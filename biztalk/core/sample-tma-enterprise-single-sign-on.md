---
title: サンプル TMA:エンタープライズ シングル サインオン |Microsoft Docs
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
ms.openlocfilehash: 9c87a27ced896214e361d6056da2e1b5e13c0883
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393911"
---
# <a name="sample-tma-enterprise-single-sign-on"></a>サンプル TMA:エンタープライズ シングル サインオン
このトピックでは、サンプル アーキテクチャのエンタープライズ シングル サインオン シナリオ向けの脅威モデル分析 (TMA) について説明します。  
  
 次の図は、基盤となるサンプル アーキテクチャを示し、エンタープライズ シングル サインオンのシナリオが含まれています。  
  
 **エンタープライズ シングル サインオン シナリオを含む 1 の基盤となるサンプル アーキテクチャを図します。**  
  
 ![ベース アーキテクチャ コンポーネント](../core/media/tdi-sec-refarch.gif "tdi_sec_refarch _")  
  
## <a name="step-1-collect-background-information-enterprise-single-sign-on-scenario"></a>手順 1. 背景情報 (エンタープライズ シングル サインオン シナリオ) の収集します。  
 このセクションでは、バックエンド ネットワークへの接続に使用する資格情報に Windows 資格情報をマップする際にエンタープライズ シングル サインオン シナリオを使用するためのデータ フロー ダイアグラム (DFD) について説明します。  
  
 その他のすべての背景情報の使用シナリオ、すべて同じで既に説明した[サンプル シナリオの背景情報](../core/background-information-for-sample-scenarios.md)します。  
  
### <a name="data-flow-diagram"></a>データ フロー ダイアグラム  
 次の図は、エンタープライズ シングル サインオン シナリオ用の DFD を示しています。  
  
 **エンタープライズ シングル サインオン シナリオでは、図 2 の DFD**  
  
 ![エンタープライズ シングル サインオンの DFD&#45;で](../core/media/tdi-sec-refarch-dfd-sso.gif "TDI_Sec_RefArch_DFD_SSO")  
  
 データ フローは次のとおりです。  
  
1.  ユーザーまたはアプリケーションが Windows 資格情報を使用してログオンします。  
  
2.  エンタープライズ シングル サインオンが Windows 資格情報を使用して、バックエンド ネットワークの資格情報を要求します。  
  
3.  エンタープライズ シングル サインオンは Windows 資格情報を、SSO データベースに格納されたバックエンド資格情報にマップします。  
  
4.  エンタープライズ シングル サインオンはバックエンド資格情報を取得し、その資格情報を使用してユーザーまたはアプリケーションをバックエンド ネットワークに接続します。  
  
## <a name="step-2-create-and-analyze-the-threat-model-enterprise-single-sign-on-scenario"></a>手順 2. 作成し、分析、脅威モデル (エンタープライズ シングル サインオン シナリオ)  
 このセクションでは、サンプル アーキテクチャのエンタープライズ シングル サインオン シナリオに対して実行した TMA の結果を示します。  
  
- **エントリ ポイント、信頼の境界、およびデータ フローの特定**-手順 1 で前で説明されている背景情報を参照してください。[サンプル シナリオの背景情報](../core/background-information-for-sample-scenarios.md)します。  
  
- **特定された脅威の一覧を作成**のシナリオに潜在的な脅威を識別するために、DFD のすべてのエントリのカテゴリに分類を使いました。**S**poofing を識別、 **T**データ、ampering **R**、これが否認**は**漏洩、 **D**ービス拒否、**E**levation 特権。 次の表は、エンタープライズ シングル サインオン (SSO) を使用して BizTalk Server との間でメッセージを送受信したときに特定された脅威を示しています。  
  
  **特定された脅威の一覧を表 1**  
  
|脅威|説明|[Asset]|影響|  
|------------|-----------------|-----------|------------|  
|マスタ シークレット サーバーで単一ポイントのエラーが発生する|悪意のあるユーザーがマスタ シークレット サーバーに侵入すると、SSO コンピュータでは資格情報を暗号化できません (資格情報の暗号解読を続行できません)。|BizTalk Server および SSO 環境|サービス拒否が起こる|  
|悪意のあるユーザーが、クライアントまたはサーバーを偽装できる|クライアントまたはサーバーで NTLM 認証ではなく Windows 認証が実行される場合、悪意のあるユーザーがクライアントまたはサーバーを偽装することがあります。|BizTalk Server および SSO 環境|ID 偽装<br /><br /> データの改ざん<br /><br /> 否認<br /><br /> 情報の漏えい<br /><br /> サービス拒否が起こる<br /><br /> 特権の昇格|  
|悪意のあるユーザーが、あるサーバーから別のサーバーに移動中のデータを改ざんできる|サーバー間の通信がクリア テキストで行われていると、悪意のあるユーザーが移動中のデータを読み取る可能性があります。|data|データの改ざん<br /><br /> 情報の漏えい|  
  
## <a name="step-3-review-threats-enterprise-single-sign-on-scenario"></a>手順 3. (エンタープライズ シングル サインオン シナリオ) の脅威を確認します。  
 このセクションでは、サンプル アーキテクチャのエンタープライズ シングル サインオン (SSO) シナリオで特定された脅威に対して実行したリスク分析の結果を示します。 主要な脅威モデルは、会議後、脅威を確認し、使用のために使用、次に影響を与える各脅威のリスクを識別するカテゴリ。**D**amage、潜在的な**R**可能性、 **E**xploitability、 **A**影響を受けるユーザー、および**D**iscoverability します。  
  
 次の表は、エンタープライズ シングル サインオンを使用して BizTalk Server との間でメッセージを送受信したときに特定された脅威のリスクの度合いを示しています。  
  
 **表 2. 特定された脅威のリスクの評価**  
  
|脅威|影響|潜在的な損害|再現性|悪用性|影響を受けるユーザー|検出可能性|リスクの度合い|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|マスタ シークレット サーバーで単一ポイントのエラーが発生する|サービス拒否が起こる|2|3|2|1|2|2|  
|悪意のあるユーザーが、クライアントまたはサーバーを偽装できる|ID 偽装<br /><br /> データの改ざん<br /><br /> 否認<br /><br /> 情報の漏えい<br /><br /> サービス拒否が起こる<br /><br /> 特権の昇格|3|2|2|2|1|2|  
|悪意のあるユーザーが、あるサーバーから別のサーバーに移動中のデータを改ざんできる|データの改ざん<br /><br /> 情報の漏えい|3|1|1|2|1|1.6|  
  
## <a name="step-4-identify-mitigation-techniques-enterprise-single-sign-on-scenario"></a>手順 4. 緩和方法 (エンタープライズ シングル サインオン シナリオ) の特定します。  
 このセクションでは、サンプル アーキテクチャのエンタープライズ シングル サインオン シナリオで特定された脅威を緩和する方法について説明します。  
  
 次の表は、エンタープライズ シングル サインオンを使用したときに特定された脅威の緩和方法とテクノロジを示しています。  
  
 **表 3. 緩和方法とテクノロジ**  
  
|脅威|影響|リスクの度合い|緩和方法とテクノロジ|  
|------------|------------|-------------------|--------------------------------------------|  
|マスタ シークレット サーバーで単一ポイントのエラーが発生する|サービス拒否が起こる|2|マスタ シークレット サーバーにアクティブ/パッシブ クラスタ構成を使用します。<br /><br /> マスター シークレット サーバーをクラスタ リングの詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)します。|  
|悪意のあるユーザーが、クライアントまたはサーバーを偽装できる|ID 偽装<br /><br /> データの改ざん<br /><br /> 否認<br /><br /> 情報の漏えい<br /><br /> サービス拒否が起こる<br /><br /> 特権の昇格|2|ネットワークが Kerberos 認証をサポートしている場合、すべての SSO サーバーを登録する必要があります。 マスタ シークレット サーバーと SSO データベース間に Kerberos 認証を使用する場合は、SSO データベースが存在する SQL Server コンピュータにサービス プリンシパル名 (SPN) を構成する必要があります。<br /><br /> サービス プリンシパル名を構成する方法の詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=61374](http://go.microsoft.com/fwlink/?LinkId=61374)します。|  
|悪意のあるユーザーが、あるサーバーから別のサーバーに移動中のデータを改ざんできる|データの改ざん<br /><br /> 情報の漏えい|1.6|すべての SSO サーバーと SSO データベース間にインターネット プロトコル セキュリティ (IPsec) またはセキュア ソケット レイヤ (SSL) を使用します。<br /><br /> SSL の詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=189708](http://go.microsoft.com/fwlink/?LinkID=189708)します。<br /><br /> すべての SSO サーバーと SSO データベースの間で SSL を使用する方法の詳細については、次を参照してください。 [SSO の SSL を有効にする方法](../core/how-to-enable-ssl-for-sso.md)します。|  
  
## <a name="see-also"></a>参照  
 [脅威モデル分析](../core/threat-model-analysis.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)   
 [中小企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)