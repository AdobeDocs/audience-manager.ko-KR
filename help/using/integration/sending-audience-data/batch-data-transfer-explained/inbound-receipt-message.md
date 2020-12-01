---
description: 인바운드 Server-to-Server 파일이 처리될 때마다 파트너 솔루션에 이메일을 통해 수신기가 전송되고, 구성된 경우 파트너에게 영수증이 전송됩니다.
seo-description: 인바운드 Server-to-Server 파일이 처리될 때마다 파트너 솔루션에 이메일을 통해 수신기가 전송되고, 구성된 경우 파트너에게 영수증이 전송됩니다.
seo-title: 인바운드 처리 후 파트너에 대한 샘플 메시지
solution: Audience Manager
title: 인바운드 처리 후 파트너에 대한 샘플 메시지
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 3%

---


# 인바운드 처리 후 파트너에 대한 샘플 메시지{#sample-message-to-partners-after-inbound-processing}

인바운드 [!UICONTROL Server-to-Server] 파일이 처리될 때마다 파트너 솔루션에 이메일을 통해 수신기가 전송되고, 구성된 경우 파트너에게 영수증이 전송됩니다.

<!-- r_inbound_message.xml -->

다음은 샘플 이메일 메시지입니다. 메시지 아래 표는 메시지의 다양한 행에 대해 설명합니다.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>보낸 사람:aam-noreply@adobe.com  </b> </p> <p> <b>제목:Adobe Audience Manager 서버 간 처리 결과:</b> </p> <p> <b>Adobe 파트너 여러분:(ID:7)</b> <b></b> </p> <p> <b>귀하의 Adobe Audience Manager 서버 간 파일 배달을 받았습니다.</b> </p> <p> <b>파일 이름:</b> <i></i> </p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b><i> </i></p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b><i> </i></p> <p> <b>받은 레코드:40669900</b> </p> <p><b>형식 오류:0</b> </p> <p> <b>잘못된 AAM ID:112년  </b> </p> <p> <b>일치하는 AAM ID 없음:0  </b> </p> <p> <b>감지된 트레이트 없음:26730823  </b> </p> <p> <b>처리된 레코드:40669900  </b> </p> <p> <b>저장된 레코드:13938958  </b> </p> <p> <b>총 장치:21  </b> </p> <p> <b>총 신호:918878926  </b> </p> <p> <b>총 사용되지 않은 신호:660348376  </b> </p> <p> <b>총 실현 특성:258086908  </b> </p> <p> <b>제거된 총 특성:0  </b> </p> <p> <b>실패한 총 트레이트 유효성 검사:0  </b> </p> <p> <b>유효성 검사에 실패한 트레이트가 있는 총 사용자:0  </b> </p> <p> <b>작업 시작 시간:2018-05-17 18:07:49  </b> </p> <p> <b>작업 종료 시간:2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

다음 표에는 수신된 이메일 메시지의 줄에 해당하는 행이 포함됩니다.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 라인 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 파일 이름 </td> 
   <td colname="col2"> <p>함께 처리된 이 파트너에 대해 Adobe이 받은 모든 인바운드 파일 목록입니다. 이전 샘플 이메일 메시지에서 파트너 ID는 7이고 데이터 소유자 ID는 901입니다. </p> <p>꼬리 번호(1,2,3..)는 고객 또는 인바운드 배포자에 의해 추가된 분할 번호입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 받은 레코드 </td> 
   <td colname="col2"> <p>모든 파일에서 수신된 레코드 Adobe의 총 수입니다. 대부분의 경우 인바운드 파일의 총 줄 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 형식 오류 </td> 
   <td colname="col2"> <p>예상 형식과 일치하지 않는 줄 수입니다. 이 선들은 도착된 작업에서 인식할 수 없었다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 잘못된 AAM ID </td> 
   <td colname="col2"> <p>예상 38자리 형식과 일치하지 않는 Audience Manager UUID 수입니다. 또는 파일에 전송된 Audience Manager UUID는 숫자가 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 일치하는 AAM ID 없음 </td> 
   <td colname="col2"> <p>Audience Manager이 일치하는 UUID를 찾지 못한 총 사용자 수입니다. 이러한 파일은 ID가 동기화되지 않았으므로 Audience Manager에서 UUID를 찾을 수 없습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 감지된 트레이트 없음 </td> 
   <td colname="col2"> <p>라인 상의 신호가 Audience Manager 트레이트에 매핑되지 않는 레코드 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 처리된 레코드 </td> 
   <td colname="col2"> <p>처리된 총 레코드 Audience Manager 수입니다. 대부분의 경우 이 숫자는 "받은 레코드"와 같아야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 저장된 레코드 </td> 
   <td colname="col2"> <p>시스템에 데이터를 로드하게 되는 레코드 수 = 처리된 레코드 - 형식 오류 - 잘못된 AAM ID - 일치하는 AAM ID 없음 - 감지된 트레이트 없음 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 총 장치 수 </td> 
   <td colname="col2"> <p>시스템에 데이터를 로드한 장치 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 총 신호 </td> 
   <td colname="col2"> <p> 모든 인바운드 파일의 모든 사용자에 대한 총 신호 수(처리된 레코드의 총 키/값 쌍 수). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 총 미사용 신호 </td> 
   <td colname="col2"> <p>모든 인바운드 파일의 모든 사용자에 대해 사용되지 않은 총 신호 수입니다(Audience Manager 트레이트에 매핑되지 않은 키/값 쌍). 대부분의 경우 Audience Manager에 신호에 대해 정의된 규칙이 없음을 의미합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 총 실현 특성 </td> 
   <td colname="col2"> <p>신호에 따라 모든 인바운드 파일의 모든 사용자에 대한 Audience Manager 트레이트 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 제거된 총 트레이트 수 </td> 
   <td colname="col2"> <p> 모든 인바운드 파일에서 모든 사용자에 대해 제거된 총 트레이트 수입니다. 전체 시크의 경우, 사용자가 이전 실행에서는 특성이 있지만 현재 실행에서는 그렇지 않은 경우에 발생합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 실패한 총 트레이트 유효성 검사 </td> 
   <td colname="col2"> <p>파일 이름에 선언된 데이터 소스에 속하지 않는 트레이트의 수를 나타냅니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 유효성 검사에 실패한 트레이트가 있는 총 사용자 </td> 
   <td colname="col2"> <p>유효성 검사에 실패한 트레이트가 있는 레코드 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 작업 시작 시간 </td> 
   <td colname="col2"> <p>인바운드 작업이 시작되는 시간입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 작업 종료 시간 </td> 
   <td colname="col2"> <p>인바운드 작업이 끝나는 시간입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>