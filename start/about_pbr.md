# PBR 텍스쳐맵에 대해 알아보자

PBR은 물리 기반 렌더링(Physically based rendering)의 약자로  
PBR텍스쳐맵은 PBR 머터리얼을 비트맵 방식으로 저장해 불러오는 방식이다.

조금더 쉽게 설명하자면  
기존의 우리가 보던 이미지 텍스쳐가 있다면  
그것과 1대1로 대응하는 크기의 각 위치마다 데이터가 저장되어있는 텍스쳐가 있는 것이다.  

![](/image/about_pbr.md/pbrmap_sample.png)

<br>
<br>

# 적용

## **자바 에디션**
자바 에디션에서는 Optifine과 같은 셰이더 모드를 통해 적용할 수 있으며  
현제 사용 가능한 모드는 Optifine과 Iris Shader 두가지이다.  

<br>

### **어디에서 개발하는것이 가장 좋은가**

알다시피 Iris Shader는 모드 호환성이 비교적 훨씬 좋고 특별한 최적화 덕분에  
훨씬 더 쾌적한 환경에서 개발이 가능하다.

다만 옵티파인의 최대 장점인 확대, CTM, CEM등 여러 기능이 있다는점에서  
1.8.9 이하의 버전에서 개발을 진행할 예정이라면은  Optifine을 선택하는것이 좋다.  

Iris Shader를 사용하더라도 줌모드와 [Dynamic FPS](https://modrinth.com/mod/dynamic-fps)   
(마인크래프트를 켜놓은 상태로 플레이하지 않을때 성능을 제한시켜주는 최적화 모드)  
를 같이 사용하는것을 추천한다.

<br>

### **어떤 셰이더로 개발하는것이 좋은가**

현제 개발자들이 가장 많이 사용하는 셰이더는 아래와 같다.
- Kappa ( 고사양 )
- KappaPT ( 유로, 고사양 )
- Nostalgia ( 중간 사양 )
- NostalgiaVX ( 유로, 고사양 )
- Shrimple ( 고사양 )
- Bliss ( 중간 사양 )
- BSL ( 중간 사양 )

이 중 가장 많이 사용되는 셰이더는 RRe3 개발자의 셰이더  
- Kappa
- KappaPT
- Nostalgia
- NostalgiaVX

이며 같은 개발자의 셰이더인 만큼 PBR 표현에서도 거의 비슷한 수준을 보여준다.  
KappaPT와 NostalgiaVX는 패스트레이싱을 기반으로 한 빛 표현으로  
훨씬 높은 퀄리티의 표현력이 있지만 그만큼 매우 고사양이다.

Shrimple은 특유의 디퍼드 스타일?의 레이트레이싱으로  
빛이 오는 방향에 따라 그림자지는 노멀을 테스트하기 좋으며 ( 무료 셰이더 기준 )  

이 중에서 사용하지 말아야할 셰이더가 있다면  
밑에서 서술할 LabPBR을 지원하지 않는 고전 셰이더  
(1.16 이하에서 개발이 멈춘 셰이더및 SEUS),  
그냥 PBR리소스팩을 개발할때 쓸 정도로의 표현력은 되지 않는
BSL 기반 셰이더들 (Complementary, Astaralex)등이다.

<br>
<br>

## **베드락 에디션**
( 모바일, 닌텐도 스위치, 플레이스테이션, Xbox 전부 동일한 베드락 에디션이다. )  
베드락 에디션에서는 디퍼드 테크니컬 및 광선 추적 옵션에서 사용이 가능하다.  

광선 추적 옵션은 엔비디아와의 협업을 통해 제작된 만큼 컴퓨터에 RTX 그래픽카드나 또는 해당 옵션과 호환되는 그래픽카드가 필요하다.  
[요구 사양](https://learn.microsoft.com/en-us/minecraft/creator/documents/rtxgettingstarted?view=minecraft-bedrock-stable#requirements)  
( Playstaion 5, Xbox Series X 및 Series S 에서도 지원됨 )

디퍼드 테크니컬은 현제 안드로이드, iOS, Xbox에서 프리뷰 버전에서 사용이 가능하다.  
[디퍼드 테크니컬 사용법](/ect_guide/how_to_use_deffered.md)