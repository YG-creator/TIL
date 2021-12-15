# eclipse - Oracle 연동

oracle.jar 다운로드 -> eclipse의 프로젝트 오른쪽 클릭 -> Build Path -> Configure and Build Path -> Libraries -> class path -> Add External JARs -> ojdbc.jar 열기 -> Apply



# DBMS 연동

Java EE -> Data SourceExplorer -> Database Connections오른쪽 클릭 -> new -> DBMS선택 -> oracledriver, JAR, properties 설정 -> finish

OpenScrapbook 클릭-> name 선택 ->Database 선택 -> 쿼리 작성 -> 실행



# JDBC

>  driver loading -> connection -> statement 생성 -> query 처리 -> 로직 -> 해제 



## 	Driver load & Connection

```java
public Connection makeConnection() throws ClassNotFoundException, SQLException {
		String driver = "oracle.jdbc.OracleDriver";
		String url = "jdbc:oracle:thin:@localhost:1521:xe";
		String id = "HR";
		String pwd = "1234";
		
		Class.forName(driver);											// driver loading
		Connection con = DriverManager.getConnection(url,id,pwd);		// connection
		return con;
	}
```



## 	Statement 생성 및 쿼리처리

​	1. sql에 변수 ㄴㄴ

```sql
Statement stmt = con.createStatement();
ResultSet rs = stmt.executeQuery(sql);
```

2. sql에 변수 ㄴㄴ

```sql
PreparedStatement stmt = con.prepareStatement(sql);
stmt.setString(1, 변수);
ResultSet rs = stmt.executeQuery();
```



## 쿼리 처리 메소드

1. Execute

   모든 sql 실행

   결과값 boolean (select문만 true, 나머지는 false)

2. ExecuteQuery

   select문만 실행

   결과값 Resultset

3. ExecuteUpdate

   select문 외 실행

   INSERT / DELETE / UPDATE 관련 구문에서는 반영된 레코드의 건수를 반환합니다.

   CREATE / DROP 관련 구문에서는 -1 을 반환합니다.



# CRUD

## 	Create

## 	Read

```sql
	public void readAll() throws SQLException, ClassNotFoundException {
		//전체 조회 userTBL
		/* 1. DB 연결
		 * 2. 쿼리를 보내는 통로 생성 
		 * 3. 쿼리 보내고
		 * 4. 결과 받고
		 * 5. 연결종료
		 * 6. 결과처리
		 */
		String sql = "select * from userTBL";	
		Connection con = this.getConnection();		// Driver load + DB와 연결
		Statement stmt = con.createStatement();		// sql 실행도구 생성
		ResultSet rs = stmt.executeQuery(sql);		// 결과 받아올 객체 생성
		while(rs.next()){
			//조회한 내용을 컬렉션으로 변경
		System.out.println(rs.getString("userId")+","+rs.getString("userName")+","+rs.getInt("birthYear"));
		}
		rs.close();
		stmt.close();
		con.close();
	}
	

	public void readCondition(String data) throws ClassNotFoundException, SQLException {
		//조건 조회
		String sql = "select * from userTBL WHERE userId = ?";
		Connection con = this.getConnection();
		PreparedStatement stmt = con.prepareStatement(sql);		// 여기 다름
		stmt.setString(1, data);
		System.out.println(sql);
		ResultSet rs = stmt.executeQuery();
		while(rs.next()){
			//조회한 내용을 컬렉션으로 변경
			System.out.println(rs.getString(1)+","+rs.getString(2)+","+rs.getInt(3));
		}
		rs.close();
		stmt.close();
		con.close();
	}
```



## 	Update

### 		Insert

```java
	public void insertData() throws ClassNotFoundException, SQLException {
		//StudentTBL에 Abc1115.csv파일안의 데이터를 삽입
		String sql = "INSERT INTO studentTBL "
				+ "VALUES(990001,'addx', 17, 29, 16, 49, 43,154,'C','A','C')";
		Connection con = this.makeConnection();
		Statement stmt = con.createStatement();
		int affectedCount = stmt.executeUpdate(sql);
		if(affectedCount>0) {
			System.out.println("삽입 작업이 완료되었습니다.");
		}
		stmt.close();
		con.close();
	}

```

### 		Update

```java
	public void updateData() throws ClassNotFoundException, SQLException {
		String sql = "UPDATE studentTBL SET EMAIL = 'mult'"
				+ "WHERE email = 'addx' ";
		Connection con = this.makeConnection();
		Statement stmt = con.createStatement();
		int affectedCount = stmt.executeUpdate(sql);
		if(affectedCount>0) {
			System.out.println("업데이트 작업이 완료되었습니다.");
		}
		stmt.close();
		con.close();
	}
```

### 		객체 집어넣기

> csv 정보를 정리해서 한번에 DB에 삽입하기
>
> 1. csv 한 라인마다 객체 생성자 사용해서 정리
> 2. DB로 ? 부분에  getter를 사용해서 삽입

1. csv 정리

``` java
ScoreData class
+
	private ArrayList<ScoreData> makeList(){
		ArrayList<ScoreData> list = new ArrayList<ScoreData>();
		File file = new File("./data/Abc1115.csv");
		FileReader fr = null;
		BufferedReader br = null;
		try {
			fr = new FileReader(file);
			br = new BufferedReader(fr);
			String line = null;
			while((line=br.readLine())!=null) {
				String[] temp = line.split(",");
				int sno = Integer.parseInt(temp[0].trim());
				String email = temp[1];
				int kor = Integer.parseInt(temp[2].trim());
				int eng = Integer.parseInt(temp[3].trim());
				int math = Integer.parseInt(temp[4].trim());
				int sci = Integer.parseInt(temp[5].trim());
				int hist = Integer.parseInt(temp[6].trim());
				int total = Integer.parseInt(temp[7].trim());
				String mgr = temp[8];
				String acc = temp[9];
				String local = temp[10];
				list.add(new ScoreData(sno,email,kor,eng,math,sci,hist,total,mgr,acc,local));	
			}
		} catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} finally {
			try {
				br.close();
				fr.close();
			} catch (IOException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			
		}
		
		return list;
	}
```

2. DB에 삽입

```java
public void insertDataFromFile() throws ClassNotFoundException, SQLException {
		// 1. 파일에서 한라인 읽어서 데이터베이스에 삽입 --> 반복
		
		// 2. 파일에서 모든 라인을 읽어서 정리하고 한번에 데이터베이스 삽입 --> 좋은방법
		// 2-1. 하나의 라인을 어떤 방법으로 데이터베이스에 삽입 --> 인스턴스로 만들어서 처리하는 방법
		// 1000개의 데이터 인스턴스를 만들어서 처리한다.
		ArrayList<ScoreData> list = this.makeList();
		String sql = "INSERT INTO studentTBL "
				+ "VALUES(?,?,?,?,?,?,?,?,?,?,?)";
		Connection con = this.makeConnection();
		PreparedStatement stmt = con.prepareStatement(sql);
		// 3. 데이터베이스에 삽입을 어떻게 할 것인가?
		for(int i=0;i<list.size();i++) {
			ScoreData temp = list.get(i);
			// ?자리에 알맞은 데이터 셋팅하는 작업 --> 11개 작업을 해야함.			
			stmt.setInt(1, temp.getSno());
			stmt.setString(2, temp.getEmail());
			stmt.setInt(3, temp.getKor());
			stmt.setInt(4, temp.getEng());
			stmt.setInt(5, temp.getMath());
			stmt.setInt(6, temp.getSci());
			stmt.setInt(7, temp.getHist());
			stmt.setInt(8, temp.getTotal());
			stmt.setString(9, temp.getMgrCode());
			stmt.setString(10, temp.getAccCode());
			stmt.setString(11, temp.getLocalCode());
		
			int affectedCount = stmt.executeUpdate();
			if(affectedCount>0) {
				System.out.println("삽입 작업이 완료되었습니다.");
			}
		}
		stmt.close();
		con.close();		
	}
```

## 	Delete

```java
	public void deleteData() throws ClassNotFoundException, SQLException {
		String sql = "DELETE FROM studentTBL WHERE stdno = 990001";
		Connection con = this.makeConnection();
		Statement stmt = con.createStatement();
		int affectedCount = stmt.executeUpdate(sql);
		if(affectedCount>0) {
			System.out.println("삭제 작업이 완료되었습니다.");
		}
		stmt.close();
		con.close();
	}
```
