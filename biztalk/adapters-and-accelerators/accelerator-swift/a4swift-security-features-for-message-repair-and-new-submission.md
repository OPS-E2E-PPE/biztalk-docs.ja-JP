---
title: Message Repair and New Submission のセキュリティ機能によって A4SWIFT |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, messages
- A4SWIFT, security
- security, A4SWIFT
- messages, security
ms.assetid: c34bcba7-fecd-4e2f-ab49-a6ccfd96198b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00170fcdca39de36290e73779881a5d697be8010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208170"
---
# <a name="a4swift-security-features-for-message-repair-and-new-submission"></a>Message Repair and New Submission の A4SWIFT セキュリティ機能
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]SWIFT メッセージの作成、修復、キーの再検証、および承認のためには、ボックスの機能を提供します。 ビジネス ユーザーは、作成、編集、および、SWIFT メッセージを使用して確認[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、財務 (FIN) メッセージの形式とユーザーのグラフィカル インターフェイスを提供します。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]A4SWIFT ランタイムによって生成される XML からエントリ/修復/キー更新検証フォームをレンダリングし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 A4SWIFT の提供、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]内の SWIFT FIN メッセージ型を開くことができるため、メッセージの種類 (対応する A4SWIFT XSD スキーマに基づく) を各 FIN 用のテンプレート[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]です。 A4SWIFT は、セキュリティに役立つ次の機能を提供します。  
  
## <a name="infopath-forms"></a>InfoPath フォーム  
 を介して、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] FormGenerator ユーティリティを使用して生成されている A4SWIFT、によってビジネス ユーザーの送信、SWIFT を取得フォームは、メッセージの受信トレイが送受信して、送信トレイ用の 実装済みのセキュリティで保護された Windows SharePoint Services Web フォルダーです。 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]Web フォルダーのセキュリティが完全にで提供される[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]ファイル システム アクセス制御リスト (Acl) を使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびインターネット インフォメーション サービス (IIS) のセキュリティ機能です。 間で"に送信中にデータが保護されている[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]Web フォルダーと[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]で Secure Sockets Layer (SSL) と HTTPS トランスポート プロトコル。  
  
 A4SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームが作成された「信頼されていない」。 この状態は、最高レベルのセキュリティを提供します。 詳細については、信頼できる、信頼されていない、次を参照してください。 [InfoPath セキュリティ](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)です。  
  
## <a name="runtime-service"></a>ランタイム サービス  
 A4SWIFT、ランタイムに提供 (BizTalk オーケストレーションとして実装) サービスを認証するための検証、処理、および SharePoint Web フォルダー、メッセージの修復/entry オーケストレーション、バックエンド システムとの間、最終的に SWIFT SWIFT メッセージのルーティングネットワークです。 このランタイム サービスは、A4SWIFT Message Repair and New Submission と呼ばれます。  
  
## <a name="secure-messages"></a>セキュリティで保護されたメッセージ  
 記憶域と SWIFT の配信の間でメッセージを[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、および Message Repair and New Submission が基になるサービスでセキュリティ保護 ([!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、IIS、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]) とトランスポート プロトコル (SSL、HTTPS など)。 ただし、メッセージの作成、修復、承認、および送信インフラストラクチャから成るメッセージを修復し、新しい送信[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、および[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]完全性と SWIFT メッセージの保護を適用するその他のユーザー レベルのセキュリティが必要ですエンドユーザーによって処理されます。  
  
 A4SWIFT も定義し、SWIFT メッセージの変更し、信頼と権限のあるユーザーによってのみ送信されること、およびメッセージのデータの変更または送信の非同期の手順を実行中に改ざんされていないかどうかを確認するためのユーザー レベルのセキュリティのセマンティクスを実装(たとえば、作業中のメッセージがユーザーの関与を待機している SharePoint Web フォルダーに格納されています) を処理します。 調整して、ワークステーションのセキュリティ機能を構成する (を通じて[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]) (A4SWIFT Message Repair and New Submission) を使用してサーバーがこれらのユーザー レベルのセキュリティ ポリシーを適用します。