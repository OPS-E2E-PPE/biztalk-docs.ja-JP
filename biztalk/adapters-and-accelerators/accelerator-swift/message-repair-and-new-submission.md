---
title: "Repair and New Submission をメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages
- resubmitting messages
- errors, messages
- messages, errors
- messages, resubmitting
ms.assetid: 5bc6bfa2-8210-4dd3-89bb-5455e294ca92
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bc15351848fe68d6ef54c31fc6d58c075bb1c58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-repair-and-new-submission"></a>Message Repair and New Submission
メッセージ修復 and New Submission 機能[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]MT および MX メッセージの検証に失敗を修復するための手段を提供します。 (ユーザーが展開されている) MRSR SharePoint サイトを使用して表示できます、メッセージが検証に失敗しました。 MRSR サイトからを使用すると、エラーを特定し、メッセージの修復、再処理のために送信する InfoPath フォームのメッセージを開くことができます。  
  
 Message Repair and New Submission ロール ベースのメッセージの修復をサポートします。 完全修復ワークフローには、修復、確認、および承認が含まれています。 修復ワークフローは、ワークフローのロール (または段階) を定義し、各ロールに対して、A4SWIFT ユーザーを構成する部門に関連付けられます。 各修復ロールには、ロールに合わせて個別 MRSR サイト ビューがあります。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]検証、および各 A4SWIFT を実行するユーザー ロール記号、メッセージ セキュリティで保護された処理を行うため、証明書の使用を実行します。  
  
 メッセージの修復に加えて A4SWIFT を使用すると、拡張を使用して、新しいメッセージを送信する[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 4 番目の A4SWIFT ユーザーの作成者は、この関数を実行します。 また、プロセスは、検証を実行し、送信が成功したことを確認する修復、確認、および承認のロールを含めることができます。 A4SWIFT ハンドルから新しいメッセージの送信、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]修復されたメッセージを処理する同じ方法を形成します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [メッセージの修復処理](../../adapters-and-accelerators/accelerator-swift/message-repair-process.md)  
  
-   [Message Repair and New Submission の部門とロールの作成](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)  
  
-   [InfoPath フォームを使用してメッセージを修復または、新しいメッセージを送信](../../adapters-and-accelerators/accelerator-swift/using-an-infopath-form-to-repair-a-message-or-submit-a-new-message.md)  
  
-   [Message Repair and New Submission の特別な処理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)  
  
-   [未解析のメッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)  
  
-   [Message Repair and 新しい送信サービスの処理](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-service-processing.md)