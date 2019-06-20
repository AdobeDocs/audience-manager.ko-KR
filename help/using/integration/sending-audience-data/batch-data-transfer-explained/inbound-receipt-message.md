---
description: 인바운드 서버 대 서버 파일이 처리될 때마다, 영수증은 파트너 솔루션에 이메일을 통해 전송되고, 구성된 경우 파트너에게 전송됩니다.
seo-description: 인바운드 서버 대 서버 파일이 처리될 때마다, 영수증은 파트너 솔루션에 이메일을 통해 전송되고, 구성된 경우 파트너에게 전송됩니다.
seo-title: 인바운드 처리 후 파트너에게 메시지 샘플
solution: Audience Manager
title: 인바운드 처리 후 파트너에게 메시지 샘플
uuid: 69 E 3 A 8 B 3-8465-4 F 4 C -8005-8 A 9 FF 15 AE 19 A
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Sample Message to Partners after Inbound Processing{#sample-message-to-partners-after-inbound-processing}

Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.

<!-- r_inbound_message.xml -->

다음 예는 샘플 이메일 메시지입니다. 메시지 아래 표는 메시지의 다양한 행에 대해 설명합니다.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>보낸 사람: aam-noreply@adobe.com </b> </p> <p> <b>제목: Adobe Audience Manager 서버-서버-서버 처리 결과:</b> </p> <p> <b>Adobe 파트너님께 (ID: 7)</b><b></b> </p> <p> <b>Adobe Audience Manager 서버-서버 파일 배달을 받았습니다.</b> </p> <p> <b>파일 이름:</b><i></i> </p> <p> <b> s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806402. sync</b> </p> <p> <b> s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-16/ftp_ dpm_ 7_ 901_ 1368655202. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784804. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806403. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784802. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784803. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806404. sync</b> </p> <p> <b>받은 레코드: 40669900</b> </p> <p><b>형식 오류: 0</b> </p> <p> <b>잘못된 AAM ID: 112 </b> </p> <p> <b>일치하는 AAM ID 없음: 0 </b> </p> <p> <b>특징이 없습니다. 26730823 </b> </p> <p> <b>처리된 레코드: 40669900 </b> </p> <p> <b>저장된 레코드: 13938958 </b> </p> <p> <b>총 장치: 21 </b> </p> <p> <b>총 신호: 918878926 </b> </p> <p> <b>사용되지 않은 총 신호 수: 660348376 </b> </p> <p> <b>총 구현된 특성: 258086908 </b> </p> <p> <b>제거된 총 트레이트: 0 </b> </p> <p> <b>총 품질 실패 유효성 검사: 0 </b> </p> <p> <b>확인하지 못한 트레이트가 있는 총 사용자 수: 0 </b> </p> <p> <b>작업 시작 시간: 2018-05-17 18:07:49 </b> </p> <p> <b>작업 종료 시간: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

다음 표에는 수신된 이메일 메시지의 행에 해당하는 행이 포함되어 있습니다.

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
   <td colname="col2"> <p>함께 처리된 이 파트너에 대해 Adobe가 받은 모든 인바운드 파일 목록. 이전 샘플 이메일 메시지에서 파트너 ID는 7 이고 데이터 소유자 ID는 901 입니다. </p> <p>테일 번호 (1,2,3...) 는 고객 또는 인바운드 배포자에 의해 추가된 분할 번호입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 받은 레코드 </td> 
   <td colname="col2"> <p>모든 파일에서 Adobe가 받은 총 레코드 수입니다. 대부분의 경우, 인바운드 파일의 총 줄 수가 되어야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 형식 오류 </td> 
   <td colname="col2"> <p>예상 형식과 일치하지 않는 라인 수입니다. 이러한 라인은 인바운드 작업에서 인식할 수 없었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 잘못된 AAM ID </td> 
   <td colname="col2"> <p>예상 38 자리 형식이 일치하지 않는 Audience Manager UUIDS의 수입니다. 또는 파일에서 보낸 Audience Manager UUID는 숫자가 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 일치하는 AAM ID 없음 </td> 
   <td colname="col2"> <p>Audience Manager가 일치하는 UUID를 찾지 못한 총 사용자 수입니다. 이러한 파일은 ID 동기화되지 않았으므로 Audience Manager에서 UUID를 찾을 수 없습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 실현되는 특성 없음 </td> 
   <td colname="col2"> <p>대상 관리자 트레이트에 대한 라인 맵에서 어떤 신호가 포함되지 않은 레코드 수. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 처리된 레코드 </td> 
   <td colname="col2"> <p>Audience Manager가 처리된 총 레코드 수입니다. 대부분의 경우 이 번호는 "받은 레코드" 와 같아야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 저장된 레코드 </td> 
   <td colname="col2"> <p>시스템 = 기록 처리 - 형식 오류 - AAM ID가 없는 잘못된 AAM ID - 잘못된 AAM ID로 로드할 수 있는 레코드 수. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 총 장치 수 </td> 
   <td colname="col2"> <p>데이터를 시스템에 로드한 장치 수. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 총 신호 수 </td> 
   <td colname="col2"> <p> 모든 인바운드 파일에서 모든 사용자에 대한 총 신호 수입니다 (처리된 레코드의 총 키/값 쌍 수). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 사용되지 않은 총 신호 수 </td> 
   <td colname="col2"> <p>모든 인바운드 파일 (Audience Manager 트레이트에 매핑되지 않은 키/값 쌍) 의 모든 사용자에 대해 사용되지 않은 총 신호 수입니다. 대부분의 경우 Audience Manager 에는 신호에 대해 정의된 규칙이 없습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 총 구현 특성 </td> 
   <td colname="col2"> <p>신호를 기준으로 모든 인바운드 파일에 대한 Audience Manager 트레이트의 수 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 제거된 총 트레이트 수 </td> 
   <td colname="col2"> <p> 모든 인바운드 파일에서 모든 사용자에 대해 제거된 총 트레이트 수입니다. 전체 동기화의 경우, 사용자가 이전 실행에서는 트레이트, 현재 실행에는 이 속성이 없을 경우 발생합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 총 품질 실패 유효성 검사 </td> 
   <td colname="col2"> <p>파일 이름에서 선언된 데이터 소스에 속하지 않는 트레이트 수를 나타냅니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 인증에 실패한 트레이트가 있는 총 사용자 수 </td> 
   <td colname="col2"> <p>확인하지 못한 트레이트가 있는 레코드 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 작업 시작 시간 </td> 
   <td colname="col2"> <p>인바운드 작업이 시작된 시간입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 작업 종료 시간 </td> 
   <td colname="col2"> <p>인바운드 작업이 종료되는 시간입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>