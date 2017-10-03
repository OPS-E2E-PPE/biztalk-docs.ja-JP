---
title: "会社 A のセキュリティに関するケース スタディ: |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 9417ecf9-e340-479f-b120-552c62f3b189
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1f48edfc2ab2228d910a0729025fd7b4da117f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-case-studies-company-a"></a>セキュリティに関するケース スタディ: 会社 A
会社 A は、原料供給業者の大手であり、工業部門にサービスを提供します。 この会社のビジネス モデルは、主要な顧客および業者との電子商取引に依存しています。 会社 A では、Microsoft BizTalk アプリケーションを使用して、トランザクションと内部および外部の環境間の通信を管理します。  
  
## <a name="potential-threats-and-security-concerns"></a>潜在的な脅威とセキュリティの問題  
 会社 A は、認証された送信元からのメッセージのみを処理したいと考えています。 BizTalk Server で処理するドキュメントには、財務や人事に関するデータなどの機密情報が含まれている場合があります。 会社 A は、カスタム暗号化 API を使用して各着信メッセージを検証します。 また、自社の物理アーキテクチャを構築してセキュリティのニーズに対処しています。  
  
 会社 A は、一部のメッセージ トラフィックにファイル転送プロトコル (FTP) を使用します。 FTP は本質的にセキュリティで保護されていませんが、会社 A は、外部に接続された他のアプリケーションをセキュリティで保護できるように多くのファイアウォールを備えているため、関連するリスクを認めたうえで使用しています。 会社 A は着信データの一部を HTTPS 経由で受信するため、外部の送信元からのサービス拒否 (DoS) 攻撃について懸念しています。 DoS 攻撃が発生した場合、会社には、すぐに担当者に警告するメカニズムがあります。  
  
## <a name="security-architecture"></a>セキュリティのアーキテクチャ  
 次の図は、会社 A が使用するセキュリティ アーキテクチャを示しています。 この会社はフロントエンドのアプリケーションとコンテンツ サーバー、バックエンドのデータベースとビジネス ロジック サーバー、および送信メッセージ インフラストラクチャを保護できるように、ファイアウォールを使用してその環境をセグメント化したことに注意してください。  
  
 **図 1. 会社 A のセキュリティ アーキテクチャ**  
  
 ![会社のセキュリティ アーキテクチャ](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")  
  
 会社 A には、BizTalk Server との間で情報を送受信する主な方法が 2 とおりあります。 1 つ目の方法では、FTP を使用します。 会社 A は、サード パーティの変換サービス プロバイダを使用して業者やパートナーと通信することにより、電子データ交換 (EDI) トランザクションをサポートします。 このサード パーティの変換サービス プロバイダは、BizTalk Server が EDI 形式で処理する必要のある注文の送受信を処理します。  
  
 2 つ目の方法では HTTPS を使用します。 会社 A は、自社が販売および消費する製品の購入と販売を容易に行えるように、その業界で中心的な役割のサード パーティ製サービス プロバイダを使用しています。  
  
## <a name="secure-digital-certificates"></a>セキュリティで保護されたデジタル証明書  
 会社 A は、セキュリティで保護された独自のデジタル証明書を実装しています。 会社 A で管理する証明書はごくわずかです。 会社 A ではサード パーティのサービス プロバイダを使用しているため、デジタル証明書についてあまり懸念していません。 サービス プロバイダはさまざまな機関と連携するため、デジタル証明書がサービス プロバイダにとって非常に重要であることを会社 A は認識しています。  
  
## <a name="see-also"></a>参照  
 [中小規模の企業のセキュリティのケース スタディ](../core/security-case-studies-for-small-to-medium-sized-companies.md)    
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)