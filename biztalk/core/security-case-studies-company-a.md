---
title: セキュリティに関するケース スタディ:会社 A |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 9417ecf9-e340-479f-b120-552c62f3b189
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 213dfa9cb7664b96a867beed944698f71da9bb4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251054"
---
# <a name="security-case-studies-company-a"></a>セキュリティに関するケース スタディ:会社 A
会社 A は、マテリアルと、工業部門にサービスの主要なサプライヤーです。 そのビジネス モデルは、主要な顧客とサプライヤーの電子商取引に依存しています。 会社 A では、Microsoft BizTalk アプリケーションを使用して、トランザクションと内部および外部の環境間の通信を管理します。  
  
## <a name="potential-threats-and-security-concerns"></a>潜在的な脅威とセキュリティに関する注意事項  
 会社 A は、認証された送信元からのメッセージのみを処理するかどうかを確認する必要があります。 BizTalk Server で処理するドキュメントの一部などの機密情報を格納できます財務および人事データ。 会社 A は、カスタム暗号化 Api を使用して、各受信メッセージを確認します。 セキュリティのニーズを処理するために、物理アーキテクチャにも構築します。  
  
 会社 A は、メッセージ トラフィックの一部のファイル転送プロトコル (FTP) を使用します。 FTP はセキュリティで保護された本質的にありませんが、会社 A は、他の外部に接続するアプリケーションを保護するために多くのファイアウォールがあるため、関連するリスクを受け入れます。 会社 A は、HTTPS 経由の受信データの一部を受信するため、サービス拒否 (DoS) 攻撃の外部ソースからについて懸念しています。 DoS 攻撃が発生した場合、企業は、適切な人にすぐに警告するメカニズムを持っています。  
  
## <a name="security-architecture"></a>セキュリティのアーキテクチャ  
 次の図は、会社 A を使用するセキュリティ アーキテクチャを示しています。 フロント エンドのアプリケーションとコンテンツ サーバー、そのバックエンド データベースとビジネス ロジック サーバー、および送信メッセージ インフラストラクチャを保護するためにファイアウォールを使用してその環境をセグメント化したことに注意してください。  
  
 **図 1. 会社 A セキュリティ アーキテクチャ**  
  
 ![会社のセキュリティ アーキテクチャ](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")  
  
 会社 A には、BizTalk Server との情報を送受信する 2 つの主な方法があります。 最初のメソッドは、FTP を使用します。 電子データをサポートして、会社 A は、業者やパートナーとの通信にサード パーティの変換サービス プロバイダーを使用して、(EDI) トランザクションを交換します。 このサード パーティの変換サービス プロバイダーは、BizTalk Server が EDI 形式で処理する必要があります着信および発信の注文を処理します。  
  
 会社 A を使用する 2 番目のメソッドは、HTTPS です。 会社 A は、その業界のハブとして機能し、購入と販売製品、自社が販売しているし、簡単に使用するサード パーティのサービス プロバイダーでも機能します。  
  
## <a name="secure-digital-certificates"></a>デジタル証明書をセキュリティで保護します。  
 会社 A は、独自のセキュリティで保護されたデジタル証明書を実装します。 いくつかの証明書のみを管理します。 サード パーティのサービス プロバイダーを使用しているためには、デジタル証明書についてあまり懸念していません。 会社 A は、サービス プロバイダーがさまざまな機関と対話するために、サービス プロバイダーにとってをデジタル証明書を気付きます。  
  
## <a name="see-also"></a>参照  
 [中小規模の企業のセキュリティのケース スタディ](../core/security-case-studies-for-small-to-medium-sized-companies.md)    
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)