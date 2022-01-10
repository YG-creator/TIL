# open api

> 병원 open api ex

```java
	public void hp_id(hospitalVO hosp) {	// 병원 위치 찾기
		String servicekey = "EWdxpP6bbAOIpmqp0unjTiqqLOwllK5fOBPhvZhqRYZkEBksUGXGIMuzoe7HJPqUisG8YhgOnzYkYtBUwOC0ow%3D%3D";	//인증코드
		int pageNo = 1;	//입력 사항
		String numOfRows = "100";	//입력 사항
		try{
			while(true){
				String url = "http://apis.data.go.kr/B552657/HsptlAsembySearchService/getHsptlMdcncLcinfoInqire?serviceKey="+servicekey+"&WGS84_LON="+hosp.getLang()+
						"&WGS84_LAT="+hosp.getLat()+"&pageNo="+Integer.toString(pageNo)+"&numOfRows="+numOfRows;	//url
			
				DocumentBuilderFactory dbFactoty = DocumentBuilderFactory.newInstance();
				DocumentBuilder dBuilder = dbFactoty.newDocumentBuilder();
				Document doc = dBuilder.parse(url);
				
				// root tag 
				doc.getDocumentElement().normalize();
				//System.out.println("Root element :" + doc.getDocumentElement().getNodeName());
				// 파싱할 tag
				NodeList nList = doc.getElementsByTagName("item");	//item 부분 상황에 맞게 바꿔라
				//System.out.println("파싱할 리스트 수 : "+ nList.getLength());
				
				for(int temp = 0; temp < nList.getLength(); temp++){
					Node nNode = nList.item(temp);
					if(nNode.getNodeType() == Node.ELEMENT_NODE){
						
						Element eElement = (Element) nNode;
						System.out.println("병원코드  : " + getTagValue("hpid", eElement));	//hpid만 출력
                    }
                }
            }
		} catch (Exception e){	
			e.printStackTrace();
		}	// try~catch end
	}	// main end
```



