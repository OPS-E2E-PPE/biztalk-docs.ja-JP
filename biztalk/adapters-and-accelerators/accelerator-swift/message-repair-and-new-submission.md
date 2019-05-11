---
title: Message Repair and New Submission |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- resubmitting messages
- errors, messages
- messages, errors
- messages, resubmitting
ms.assetid: 5bc6bfa2-8210-4dd3-89bb-5455e294ca92
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e17faaf34279140dd67fa3c82c69805db91d4f5d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530276"
---
# <a name="message-repair-and-new-submission"></a>Message Repair and New Submission
メッセージの修復 and New Submission 機能[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]検証に失敗したメッセージを MT と MX を修復するための手段を提供します。 (ユーザーによってデプロイされる) MRSR SharePoint サイトを使用して、メッセージが検証に失敗しましたを確認できます。 MRSR サイトからを InfoPath フォーム エラーを特定、修復、メッセージを再処理するために送信することができるメッセージを開くことができます。  
  
 Message Repair and New Submission は、ロール ベースのメッセージの修復をサポートしています。 完全修復がワークフローには、修復、確認、および承認が含まれています。 修復のワークフローは、ワークフローのロール (または段階) を定義して、A4SWIFT ユーザーの各ロールを構成する部門に関連付けられます。 各修復ロールには、ロールに合わせて個別 MRSR サイト ビューがあります。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 検証、および各 A4SWIFT を実行するユーザー ロールの署名、メッセージ セキュリティで保護された処理を行うため、証明書を使用して実行します。  
  
 メッセージの修復に加えて A4SWIFT を使用すると、拡張を使用して新しいメッセージ送信[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 4 番目の A4SWIFT ユーザーの作成者は、この関数を実行します。 また、プロセスは、検証を実行し、送信が成功したことを確認して、修復、確認、および承認のロールを含めることができます。 A4SWIFT 処理から新しいメッセージの送信、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]修復されたメッセージを処理する同じ方法を形成します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [メッセージの修復処理](../../adapters-and-accelerators/accelerator-swift/message-repair-process.md)  
  
-   [Message Repair and New Submission 用に部門とロールを作成する](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)  
  
-   [InfoPath フォームを使用してメッセージを修復または新しいメッセージを送信する](../../adapters-and-accelerators/accelerator-swift/using-an-infopath-form-to-repair-a-message-or-submit-a-new-message.md)  
  
-   [Message Repair and New Submission での特殊な処理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)  
  
-   [未解析メッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)  
  
-   [Message Repair and New Submission サービスの処理](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-service-processing.md)