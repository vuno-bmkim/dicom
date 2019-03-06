# DICOM (작성중)
# 1. 개요
* Digital Imaging and Communications in Medicine (의료용 디지털 영상 및 통신 표준)
* 방사선 촬영, 초음파 검사, CT촬영, MRI촬영 등 다양한 의료용 영상 촬영 기기가 개발되고, 이렇게 획득한 영상의 활용이 다양해짐 
  * PACS (Picture Archiving and Communication System, 의료영상 저장전송시스템) : 의료용 영상을 저장 및 전송하고 관리하는 솔루션
* 이에 따라 제조업체/영상종류 등에 무관하게 의료용 영상을 통합하여 저장/관리/조회/가공/통신하기 위한 “표준 포맷"이 필요해짐
* 1985년에 최초 표준인 ACR/NEMA 300이 출시되었고, 수정을 거쳐 1993년에 출시된 버젼부터 DICOM이라는 이름으로 사용됨 
* DICOM 표준을 따르는 파일의 확장자는 .dcm 
# 2. DICOM 포맷
* DICOM 파일은 "File meta information header"와 "Information object"로 구성됨
* File meta information header
  * File Preamble (128byte)
    * 특별한 사용이나 application profile을 위하여 사용될 수 있음. 
  * DICOM prefix (4byte)
    * 해당 파일이 DICOM 파일임을 표시하기 위해, File preamble 뒤에 4byte로 "DICM"을 표시 (44 49 43 4D)
  * File Meta elements
    * Data Element (Tag (4byte) + Value Representation (2byte) + Value length (2 or 4byte) + Value Field) 의 모음으로 구성됨 
    * Tag (4 bytes)
      * Group number (2 bytes) + element number (2 bytes) 로 구성됨 
      * 해당 Tag는 특정 Attribute를 지시하며, 각 Attribute는 특정 Information Entity, 특정 Module에 속함.
    * VR (Value Representation)
      * 각 Tag가 지시하는 Attribute값의 타입
* Information object
  * 이미지/영상 데이터
![dicom_file_hexdump](./image/dicom_file_hexdump.png)
# 3. 관련 링크 
* https://en.wikipedia.org/wiki/DICOM
* https://ko.wikipedia.org/wiki/의료용_디지털_영상_및_통신_표준
* https://blog.naver.com/infinitt-healthcare/220902279599
* https://ko.wikipedia.org/wiki/의료영상저장전송시스템
* https://blog.naver.com/infinitt-healthcare/220885977992
* http://cgac.chungbuk.ac.kr/Uploads/LECTURE/DICOM-COOKBOOk.doc
* SOP Class UID : https://www.dicomlibrary.com/dicom/sop/
* transfer syntax UID : https://www.dicomlibrary.com/dicom/transfer-syntax/

