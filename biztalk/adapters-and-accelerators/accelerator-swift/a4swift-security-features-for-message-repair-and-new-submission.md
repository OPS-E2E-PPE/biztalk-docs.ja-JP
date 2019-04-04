---
title: Message Repair and New Submission のセキュリティ機能を A4SWIFT |Microsoft Docs
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
ms.openlocfilehash: ff2a4960d95b46ae8c224c17ff279719d51d8b37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986043"
---
# <a name="a4swift-security-features-for-message-repair-and-new-submission"></a>Message Repair and New Submission の A4SWIFT セキュリティ機能
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT メッセージの作成、修復、キーの再検証、および承認のためには、ボックスの機能を提供します。 ビジネス ユーザーの作成、編集、および Microsoft を使用して SWIFT メッセージを確認して[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、財務 (FIN) メッセージのグラフィカル表現とユーザー インターフェイスを提供します。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] A4SWIFT ランタイムによって生成される XML からキーを再入力エントリ/修復/検証フォームをレンダリングし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 A4SWIFT の提供、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]各 FIN 用のテンプレート メッセージの種類 (対応する A4SWIFT XSD スキーマに基づく) では、SWIFT FIN メッセージの種類を開くことができるように[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]します。 A4SWIFT では、セキュリティ支援するために、次の機能を提供します。  
  
## <a name="infopath-forms"></a>InfoPath フォーム  
 を通じて、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] A4SWIFT、によってビジネス ユーザーが送信され、SWIFT を取得、FormGenerator ユーティリティで生成されたフォームとの間の受信トレイのメッセージし、送信トレイ用の実装でのセキュリティで保護された Windows SharePoint Services Web フォルダー。 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] Web フォルダーのセキュリティは、Microsoft によって完全に提供される[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]ファイル システム アクセス制御リスト (Acl) を使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびインターネット インフォメーション サービス (IIS) のセキュリティ機能。 間"の送信中にデータが保護されている[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]Web フォルダーと[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]で Secure Sockets Layer (SSL) と HTTPS トランスポート プロトコル。  
  
 A4SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームが作成されると、「信頼されていない」。 このステータスは、最高レベルのセキュリティを提供します。 詳細については、信頼できる、信頼されていない、[InfoPath セキュリティ](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)を参照してください。  
  
## <a name="runtime-service"></a>ランタイム サービス  
 A4SWIFT ランタイムを提供します (BizTalk オーケストレーションとして実装された) サービスを認証するための検証、処理、および SharePoint Web フォルダー、メッセージの修復/エントリ オーケストレーション、バックエンド システムとの間、最終的に、SWIFT、SWIFT メッセージのルーティングネットワーク。 このランタイム サービスは、A4SWIFT Message Repair and New Submission と呼ばれます。  
  
## <a name="secure-messages"></a>セキュリティで保護されたメッセージ  
 記憶域と SWIFT の配信の間でメッセージを[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、および Message Repair and New Submission は、基になるサービスでセキュリティ保護は ([!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、IIS、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]) とトランスポート プロトコル (SSL、HTTPS)。 ただし、メッセージの作成、修復、承認、および送信のインフラストラクチャで構成メッセージ修復 and New Submission は、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、および[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]信頼性と SWIFT のメッセージの保護を適用するその他のユーザー レベルのセキュリティが必要ですエンドユーザーによって処理されます。  
  
 A4SWIFT も定義し、SWIFT メッセージが変更され、信頼および承認済みのユーザーのみが送信されたこと、およびメッセージのデータの変更または送信の非同期の手順を実行中に改ざんされていないかどうかを確認するユーザー レベルのセキュリティのセマンティクスを実装します。(たとえば、中にメッセージがユーザーの介入を待機している SharePoint Web フォルダーに格納されています) を処理します。 調整および構成すると、ワークステーションのセキュリティ機能 (を通じて[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]) および (A4SWIFT Message Repair and New Submission) を使用してサーバーがこれらのユーザー レベルのセキュリティ ポリシーを適用します。