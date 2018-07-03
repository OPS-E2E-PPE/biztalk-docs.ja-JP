---
title: 'サンプル TMA: HTTP アダプターと SOAP アダプター |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- DFD, HTTP adapters
- security examples [TMA], SOAP adapters
- SOAP adapters, examples
- security examples [TMA], HTTP adapters
- examples, HTTP adapters
- DFD, SOAP adapter
- examples, SOAP adapters
- SOAP adapters, TMA
- HTTP adapters, TMA
ms.assetid: d9a40cff-92a1-4bc9-ae45-3a5857f70222
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd1b58a89ce123350ba3b6d7be0e665d4428429a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011483"
---
# <a name="sample-tma-http-and-soap-adapters"></a>サンプル TMA: HTTP アダプターと SOAP アダプター
このトピックでは、サンプル アーキテクチャの HTTP アダプターと SOAP (Web サービス) アダプター シナリオ向けの脅威モデル分析 (TMA) について説明します。 次の図は、HTTP アダプタと SOAP アダプタ シナリオのサンプル アーキテクチャを示しています。  
  
 **図 1. HTTP/SOAP アダプタ シナリオのサンプル アーキテクチャ**  
  
 ![HTTP または SOAP アダプターのアーキテクチャのサンプル](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
## <a name="step-1-collect-background-information-http-and-soap-adapters-scenario"></a>手順 1. 背景情報 (HTTP と SOAP アダプタ シナリオ) の収集します。  
 このセクションでは、サンプル アーキテクチャの HTTP アダプタと SOAP (Web サービス) アダプタ シナリオ向けのデータ フロー ダイアグラム (DFD) について説明します。  
  
 その他のすべての背景情報の使用シナリオ、すべて同じで既に説明した[サンプル シナリオの背景情報](../core/background-information-for-sample-scenarios.md)します。  
  
### <a name="data-flow-diagram"></a>データ フロー ダイアグラム  
 次の図は、HTTP アダプタと SOAP (Web サービス) アダプタを使用する際の、サンプル アーキテクチャの DFD を示しています。  
  
 **図 2. DFD、HTTP/SOAP アダプタ シナリオのサンプル アーキテクチャ**  
  
 ![サンプル アーキテクチャの DFD](../core/media/tdi-sec-refarch-dfd-http.gif "TDI_Sec_RefArch_DFD_HTTP")  
  
 データ フローは次のとおりです。  
  
1.  パートナーや顧客が HTTP、HTTPS、または Web サービスを経由してメッセージを送信します。 メッセージはファイアウォール 1 の IP アドレスにルーティングされます。  
  
2.  ファイアウォール 1 がリバース プロキシを使用してファイアウォール 2 経由でメッセージを中継します。  
  
3.  ファイアウォール 2 から HTTP 受信アダプタまたは SOAP 受信アダプタの分離ホストのインスタンスが実行されている BizTalk Server にメッセージがルーティングされます。 分離ホストがメッセージを処理し、メッセージをメッセージ ボックス データベースに格納します。  
  
4.  メッセージへのサブスクリプションが含まれた処理ホストのインスタンスが、メッセージ ボックス データベースからそのメッセージを取得し、追加処理を行い、メッセージ ボックス データベースにメッセージを戻します。  
  
5.  HTTP 送信アダプタまたは SOAP 送信アダプタが含まれた分離ホストのインスタンスが、メッセージ ボックス データベースからメッセージを取得します。 メッセージは、送信パイプラインでの最終処理を完了してから、パートナーまたは顧客に送信されます。  
  
6.  メッセージは、パートナーや顧客に送信されると、ファイアウォール 2 経由とリバース プロキシを使用したファイアウォール 1 経由でルーティングされます。  
  
## <a name="step-2-create-and-analyze-the-threat-model-http-and-soap-adapters-scenario"></a>手順 2. 作成し、(HTTP アダプタと SOAP アダプタ シナリオ)、脅威モデル分析  
 このセクションでは、サンプル アーキテクチャの HTTP アダプタと SOAP (Web サービス) アダプタ シナリオに対して実行した TMA の結果を示します。  
  
- **特定のエントリ ポイント、信頼の境界、およびデータのフロー -** 手順 1 で前に説明されている背景情報を参照してくださいと[サンプル シナリオの背景情報](../core/background-information-for-sample-scenarios.md)します。  
  
- **-特定された脅威の一覧を作成**シナリオに潜在的な脅威を識別するために、DFD のすべてのエントリのカテゴリに分類を使いました**S**poofing を識別、 **T**ampering。データ、 **R**、これが否認**は**漏洩、 **D**ービス拒否、および**E**特権の levation。 次の表は、HTTP アダプタと SOAP アダプタを使用して BizTalk Server との間でメッセージを送受信したときに特定された脅威を示しています。  
  
  **表 1. 脅威の一覧**  
  
|脅威|説明|[Asset]|影響|  
|------------|-----------------|-----------|------------|  
|非常に大きなサイズのメッセージが送信される|悪意のあるユーザーが、非常に大きなサイズのメッセージを送信することがあります。|BizTalk Server 環境|サービス拒否が起こる|  
|受信場所に大量のメッセージが送信される|悪意のあるユーザーが、メッセージが有効であるか無効であるかに関係なくアプリケーションで受け取れないほど大量のメッセージを送信することがあります。|BizTalk Server 環境|サービス拒否が起こる|  
|HTTP 経由でメッセージ本文が読み取られる|悪意のあるユーザーが、送信者からファイアウォール 1 に移動中のメッセージを傍受し、そのメッセージを読み取ることがあります。|メッセージ ペイロード|情報の漏えい|  
|メッセージからユーザーの資格情報が読み取られる|基本認証を使用していて、メッセージにユーザーの資格情報が含まれている場合、悪意のあるユーザーが資格情報へのアクセス権を取得し、その資格情報を使用してアプリケーションにアクセスすることがあります。|ユーザーの資格情報|情報の漏えい<br /><br /> 権限の昇格|  
  
## <a name="step-3-review-threats-http-and-soap-adapters-scenario"></a>手順 3. (HTTP アダプタと SOAP アダプタ シナリオ) の脅威を確認します。  
 このセクションでは、サンプル アーキテクチャの HTTP アダプタと SOAP (Web サービス) アダプタ シナリオで特定された脅威に対して実行したリスク分析の結果を示します。 主要な脅威モデルについてのミーティング後の 脅威の確認し、各脅威のリスクを識別するために、次の影響カテゴリを使用しました**D**amage、潜在的な**R**可能性、 **E。** xploitability、 **A**影響を受けるユーザー、および**D**iscoverability します。  
  
 次の表は、HTTP アダプタと SOAP アダプタを使用して BizTalk Server との間でメッセージを送受信したときに特定された脅威のリスクの度合いを示しています。  
  
 **脅威のリスクの度合いを表 2**  
  
|脅威|影響|潜在的な損害|再現性|悪用性|影響を受けるユーザー|検出可能性|リスクの度合い|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|非常に大きなサイズのメッセージが送信される|サービス拒否が起こる|2|3|2|3|2|2.4|  
|受信場所に大量のメッセージが送信される|サービス拒否が起こる|3|3|1|3|3|2.6|  
|HTTP 経由でメッセージ本文が読み取られる|情報の漏えい|3|3|2|3|3|2.8|  
|メッセージからユーザーの資格情報が読み取られる|情報の漏えい<br /><br /> 権限の昇格|3|3|2|3|2|2.6|  
  
## <a name="step-4-identify-mitigation-techniques-http-and-soap-adapters-scenario"></a>手順 4. 緩和方法 (HTTP アダプタと SOAP アダプタ シナリオ) の特定します。  
 このセクションでは、サンプル アーキテクチャの HTTP アダプタと SOAP (Web サービス) アダプタ シナリオで特定された脅威を緩和する方法について説明します。  
  
 次の表は、HTTP アダプタと SOAP アダプタを使用して BizTalk Server との間でメッセージを送受信したときに特定された脅威の緩和方法とテクノロジを示しています。  
  
 **表 3. 緩和方法とテクノロジ**  
  
|脅威|影響|リスクの度合い|緩和方法とテクノロジ|  
|------------|------------|-------------------|--------------------------------------------|  
|非常に大きなサイズのメッセージが送信される|サービス拒否が起こる|2.4|URL ごとに着信メッセージの最大サイズを制限し、指定した最大値を超えるメッセージを拒否します。<br /><br /> 詳細については、次を参照してください。[拒否のサービス攻撃の緩和](../core/mitigating-denial-of-service-attacks.md)します。|  
|受信場所に大量のメッセージが送信される|サービス拒否が起こる|2.6|SOAP アダプタは HTTP を使用して BizTalk Server との間でメッセージを送受信します。 そのため、セキュリティに関する推奨事項に従い、インターネット インフォメーション サービス (IIS) をセキュリティで保護する必要があります。 IIS を使用している場合は、アプリケーション分離を構成する方法について IIS の推奨事項に従ってください。<br /><br /> 詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=60951](http://go.microsoft.com/fwlink/?LinkId=60951)します。<br /><br /> クライアント認証とパーティの解決を使用して、処理対象メッセージの数を有効かつ認証されたメッセージのみに制限します。|  
|HTTP 経由でメッセージ本文が読み取られる|情報の漏えい|2.8|S/MIME を使用して、BizTalk Server との間で送信されるメッセージのコンテンツをセキュリティで保護することをお勧めします。<br /><br /> Secure Sockets Layer (SSL) を使用して、BizTalk Server との間および環境に分散された BizTalk Server コンポーネント間でのデータの移動をセキュリティで保護することをお勧めします。|  
|メッセージからユーザーの資格情報が読み取られる|情報の漏えい<br /><br /> 権限の昇格|2.6|基本認証を使用する場合、またはメッセージ レベルでの暗号化を使用しない場合、SSL を使用してメッセージを送受信し、未認証のユーザーがユーザーの資格情報を読み取ることができないようにすることをお勧めします。|  
  
## <a name="see-also"></a>参照  
 [脅威モデル分析](../core/threat-model-analysis.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)   
 [中小企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)