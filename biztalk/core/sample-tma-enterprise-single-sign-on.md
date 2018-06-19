---
title: 'サンプル TMA: エンタープライズ シングル サインオン |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], SSO
- architecture, examples
- SSO, examples
- SSO, TMA
- DFD, SSO
- examples, SSO
- examples, TMA
ms.assetid: c2c15b1b-54f3-4d1a-b3d8-6679abd41ccb
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb57e7b22680844e3ddb18481aa76002df78b013
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22273194"
---
# <a name="sample-tma-enterprise-single-sign-on"></a>サンプル TMA: エンタープライズ シングル サインオン
このトピックでは、サンプル アーキテクチャのエンタープライズ シングル サインオン シナリオ向けの脅威モデル分析 (TMA) について説明します。  
  
 次の図は、基盤となるサンプル アーキテクチャを示し、エンタープライズ シングル サインオンのシナリオが含まれています。  
  
 **エンタープライズ シングル サインオン シナリオが含まれる 1 の基本のサンプル アーキテクチャを図します。**  
  
 ![ベース アーキテクチャ コンポーネント](../core/media/tdi-sec-refarch.gif "tdi_sec_refarch _")  
  
## <a name="step-1-collect-background-information-enterprise-single-sign-on-scenario"></a>手順 1. 背景情報 (エンタープライズ シングル サインオン シナリオ) の収集します。  
 このセクションでは、バックエンド ネットワークへの接続に使用する資格情報に Windows 資格情報をマップする際にエンタープライズ シングル サインオン シナリオを使用するためのデータ フロー ダイアグラム (DFD) について説明します。  
  
 その他のすべての背景情報の使用シナリオ、すべて同じでありで既に説明した[サンプル シナリオの背景情報](../core/background-information-for-sample-scenarios.md)です。  
  
### <a name="data-flow-diagram"></a>データ フロー ダイアグラム  
 次の図は、エンタープライズ シングル サインオン シナリオ用の DFD を示しています。  
  
 **エンタープライズ シングル サインオン シナリオでは、図 2 の DFD**  
  
 ![エンタープライズ シングル サインオン &#45; に対する DFD](../core/media/tdi-sec-refarch-dfd-sso.gif "TDI_Sec_RefArch_DFD_SSO")  
  
 データ フローは次のとおりです。  
  
1.  ユーザーまたはアプリケーションが Windows 資格情報を使用してログオンします。  
  
2.  エンタープライズ シングル サインオンが Windows 資格情報を使用して、バックエンド ネットワークの資格情報を要求します。  
  
3.  エンタープライズ シングル サインオンは Windows 資格情報を、SSO データベースに格納されたバックエンド資格情報にマップします。  
  
4.  エンタープライズ シングル サインオンはバックエンド資格情報を取得し、その資格情報を使用してユーザーまたはアプリケーションをバックエンド ネットワークに接続します。  
  
## <a name="step-2-create-and-analyze-the-threat-model-enterprise-single-sign-on-scenario"></a>手順 2. 作成し、分析、脅威モデル (エンタープライズ シングル サインオン シナリオ)  
 このセクションでは、サンプル アーキテクチャのエンタープライズ シングル サインオン シナリオに対して実行した TMA の結果を示します。  
  
-   **エントリ ポイント、信頼の境界、データ フローの特定**-手順 1 で前に、およびで説明されている背景情報を参照してください[サンプル シナリオの背景情報](../core/background-information-for-sample-scenarios.md)です。  
  
-   **特定された脅威の一覧を作成**-を使用して、次の分類、DFD のすべてのエントリのシナリオに潜在的な脅威を特定する: **S**poofing を識別、 **T**データを ampering **R**、これが否認**すれば**漏洩、 **D**ービス拒否、および**E**の levation権限です。 次の表は、エンタープライズ シングル サインオン (SSO) を使用して BizTalk Server との間でメッセージを送受信したときに特定された脅威を示しています。  
  
 **表 1 の脅威リスト**  
  
|脅威|Description|[Asset]|影響|  
|------------|-----------------|-----------|------------|  
|マスタ シークレット サーバーで単一ポイントのエラーが発生する|悪意のあるユーザーがマスタ シークレット サーバーに侵入すると、SSO コンピュータでは資格情報を暗号化できません (資格情報の暗号解読を続行できません)。|BizTalk Server および SSO 環境|サービス拒否が起こる|  
|悪意のあるユーザーが、クライアントまたはサーバーを偽装できる|クライアントまたはサーバーで NTLM 認証ではなく Windows 認証が実行される場合、悪意のあるユーザーがクライアントまたはサーバーを偽装することがあります。|BizTalk Server および SSO 環境|ID 偽装<br /><br /> データの改ざん<br /><br /> 否認<br /><br /> 情報の漏えい<br /><br /> サービス拒否が起こる<br /><br /> 特権の昇格|  
|悪意のあるユーザーが、あるサーバーから別のサーバーに移動中のデータを改ざんできる|サーバー間の通信がクリア テキストで行われていると、悪意のあるユーザーが移動中のデータを読み取る可能性があります。|data|データの改ざん<br /><br /> 情報の漏えい|  
  
## <a name="step-3-review-threats-enterprise-single-sign-on-scenario"></a>手順 3. 脅威の確認 (エンタープライズ シングル サインオン シナリオ)  
 このセクションでは、サンプル アーキテクチャのエンタープライズ シングル サインオン (SSO) シナリオで特定された脅威に対して実行したリスク分析の結果を示します。 主な脅威モデルについてのミーティングの後に、脅威を確認し、使用されているために使用、次に影響を与える各脅威のリスクを識別するカテゴリ: **D**amage 潜在的な**R**eproducibility、 **E**xploitability、 **A**影響を受けるユーザー、および**D**iscoverability です。  
  
 次の表は、エンタープライズ シングル サインオンを使用して BizTalk Server との間でメッセージを送受信したときに特定された脅威のリスクの度合いを示しています。  
  
 **表 2 特定された脅威のリスクの評価**  
  
|脅威|影響|潜在的な損害|再現性|悪用性|影響を受けるユーザー|検出可能性|リスクの度合い|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|マスタ シークレット サーバーで単一ポイントのエラーが発生する|サービス拒否が起こる|2|3|2|1|2|2|  
|悪意のあるユーザーが、クライアントまたはサーバーを偽装できる|ID 偽装<br /><br /> データの改ざん<br /><br /> 否認<br /><br /> 情報の漏えい<br /><br /> サービス拒否が起こる<br /><br /> 特権の昇格|3|2|2|2|1|2|  
|悪意のあるユーザーが、あるサーバーから別のサーバーに移動中のデータを改ざんできる|データの改ざん<br /><br /> 情報の漏えい|3|1|1|2|1|1.6|  
  
## <a name="step-4-identify-mitigation-techniques-enterprise-single-sign-on-scenario"></a>手順 4. 緩和方法 (エンタープライズ シングル サインオン シナリオ) の特定します。  
 このセクションでは、サンプル アーキテクチャのエンタープライズ シングル サインオン シナリオで特定された脅威を緩和する方法について説明します。  
  
 次の表は、エンタープライズ シングル サインオンを使用したときに特定された脅威の緩和方法とテクノロジを示しています。  
  
 **表 3 の緩和方法とテクノロジ**  
  
|脅威|影響|リスクの度合い|緩和方法とテクノロジ|  
|------------|------------|-------------------|--------------------------------------------|  
|マスタ シークレット サーバーで単一ポイントのエラーが発生する|サービス拒否が起こる|2|マスタ シークレット サーバーにアクティブ/パッシブ クラスタ構成を使用します。<br /><br /> マスター シークレット サーバーをクラスタ リングの詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)です。|  
|悪意のあるユーザーが、クライアントまたはサーバーを偽装できる|ID 偽装<br /><br /> データの改ざん<br /><br /> 否認<br /><br /> 情報の漏えい<br /><br /> サービス拒否が起こる<br /><br /> 特権の昇格|2|ネットワークが Kerberos 認証をサポートしている場合、すべての SSO サーバーを登録する必要があります。 マスタ シークレット サーバーと SSO データベース間に Kerberos 認証を使用する場合は、SSO データベースが存在する SQL Server コンピュータにサービス プリンシパル名 (SPN) を構成する必要があります。<br /><br /> サービス プリンシパル名を構成する方法の詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=61374](http://go.microsoft.com/fwlink/?LinkId=61374)です。|  
|悪意のあるユーザーが、あるサーバーから別のサーバーに移動中のデータを改ざんできる|データの改ざん<br /><br /> 情報の漏えい|1.6|すべての SSO サーバーと SSO データベース間にインターネット プロトコル セキュリティ (IPsec) またはセキュア ソケット レイヤ (SSL) を使用します。<br /><br /> SSL の詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=189708](http://go.microsoft.com/fwlink/?LinkID=189708)です。<br /><br /> すべての SSO サーバーと SSO データベース間で SSL を使用する方法の詳細については、次を参照してください。 [SSO の SSL を有効にする方法](../core/how-to-enable-ssl-for-sso.md)です。|  
  
## <a name="see-also"></a>参照  
 [脅威モデル分析](../core/threat-model-analysis.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)   
 [小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)