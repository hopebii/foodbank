# foodbank   
※본 프로젝트는 한국정보화진흥원(NIA)의 데이터멘토링 활동으로 진행된 데이터 분석 프로젝트입니다. 공공데이터로 제공되는 [푸드뱅크 데이터](https://www.foodbank1377.org/reference/openData.do)를 사용하여 진행하였습니다.

※또한 데이터멘토링 최종 심사 결과, 최우수(1등, 과기정통부장관상)팀으로 선정되었습니다.
### 기본 정보
<table width=80%>
  <tr><td ><b>팀 이름</b></td><td><b>프로젝트 기간</b></td><td><b>프로젝트원</b></td>
  </tr>
  <tr><td>푸잇</td><td>2022.07.23 ~ 2022.08.31</td><td><A href="https://github.com/hopebii"> 이다현</A>, <A href="https://github.com/easyofexample"> 이지예</A>, <A href="https://github.com/zzozzo"> 한승민</A></td>
  </tr>
</table>
<br/>

## 문제점 도출
자세한 문제점 도출 과정은 이 파일을 참고해주세요
<br/>

<table>
  <tr>
    <td width=20%><b>문제점 인식 과정</b></td>
    <td>  1. 코로나 바이러스 발생 이후 기부자수가 감소한 뒤 이용자수 회복 추이에 비해 더딘 회복 추이<br/>
          2. 2022년 인플레이션으로 인한 기부 감소 심화 (2022년 7월 31일 SBS 뉴스)</td>
  <tr>
    <td width=20%><b>전국 단위 데이터 분석 </b></td>
    <td>전국 단위 데이터를 분석하며 다음 3가지 공통된 특징을 가진 지역이 <b>"서울"</b>임을 확인<br/><br/>
          1. 2019년 대비 2021년 기부건수 증감률이 큰 지역 중 하나 지역<br/>
          2. 푸드뱅크 주 이용자 (이용자구분코드 기준)인 기초생활수급자와 차상위계층이 KOSIS 데이터 기준으로 많이 사는 지역<br/>
          3. 기부물품 기준 가장 다양한 물품이 기부되어 기부물품 다양성 확보가 가능한 지역<br/>   </td>
  </tr>
    <tr>
    <td width=20%><b>서울 지역 문제점 도출</b></td>
    <td>  1. 이용자 선호도를 반영한 기부자원 확보 미흡<br/>
          2. 편중된 기부 물품 카테고리<br/>
          3. 서울 푸드뱅크 이용 활성화 방안 토론회를 통한 기부 감소 문제점 대책 방안 촉구</td>
  </tr>
    <tr>
    <td width=20%><b>현행 앱 문제점 발견</b></td>
    <td>복잡한 기부과정과 부족한 정보가 제공되는 점</td>
  </tr>
  </table>
<br/>

## 제안하는 해결 방안
### 1. 클러스터링 기반 기부자-센터 매칭 서비스   
적재적소의 기부가 이뤄질 수 있도록 기부물품과 지역에 따른 기부자-센터 매칭 서비스
  - k-prototype clustering 기반의 클러스터링 진행해 4개 군집 구성
    - 연속형 변수와 범주형 변수가 혼합된 데이터이기 때문에 해당 기법 적용
  - 애플리케이션에서 기부자가 기부하고자 하는 물품과 지역을 선택하면 물품이 필요한 센터를 골라내는 알고리즘을 기반으로 센터를 추천 (해당 물품 이용자수 기준으로 needs를 설정)
<table>
  <tr>
    <td width=25%>클러스터링 수행 및 각 군집별 특징 확인</td>
    <td>
    <img src = "https://user-images.githubusercontent.com/33904461/188939448-fd39b2f6-cb4b-40dd-bc6e-5c6e8ae866b0.png">
    </td>
  </tr>
  <tr>
    <td width=25%>애플리케이션 내 적용 방안</td>
    <td>
      <img src = "https://user-images.githubusercontent.com/33904461/188940845-3510c769-d0a0-433f-b5a4-55eb11e30cd9.png">
    </td>
  </tr>
</table>   

  <br/>
  
### 2. 기부 현황 대시보드
기부자에게 기부현황과 이용에 대한 정보를 제공하는 서비스   
  - tableau를 이용한 기부 현황 및 이용 정보 시각화
<table>
<tr>
<td width = 25%>서울특별시 지역별 이용 건수 및 기부 금액 순위</td>
<td><img src = "https://user-images.githubusercontent.com/33904461/188937097-8eed4a9d-5ee8-4156-a7bc-b3b349afe7c5.png"></td>
</tr>
<tr><td width=25%>시군구별 기부금액 추이 및 기부물품 Top 5</td>
<td><img src="https://user-images.githubusercontent.com/33904461/188938070-59f09c69-944f-4515-b4a5-eb6c8660cc7d.png">
</td>
</tr>
<tr><td width=25%>지역 선호물품 신호등 및 선호물품 보유 수량</td>
<td><img src="https://user-images.githubusercontent.com/33904461/188938524-0d6de1c3-d5f4-4a3d-a027-a2dd7baa2bb1.png">
</td>
</tr>
</table>

<br/>

### 3. 1동 1푸드마켓 알림 서비스
서울광역푸드뱅크에서 시행하는 1동 1푸드마켓 활성화를 위한 이용자 특성 고려한 푸드마켓 후보지 시각화 및 기부자에게 장소 알림 서비스 제공
  - folium을 이용한 푸트마켓 후보지 시각화 
  <table>
  <tr>
    <td width=25%>
      독거어르신 이용자가 많은 양천구의 예시
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/33904461/188942290-b3902968-0f3c-4be4-8259-7737cf145c77.png"> 
    </td>
    </tr>
  </table>
<br/>

## 기대효과   
<img width=80% src = "https://user-images.githubusercontent.com/33904461/188942712-5e29c10b-1c8c-49c9-a576-82e09e85a16e.png">

