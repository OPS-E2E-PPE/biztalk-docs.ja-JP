---
title: 作成とステージの修復 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stages, repair
- stages, create
ms.assetid: 07d7ce7b-ed15-40a7-9c85-280a1d38985b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9f26752fce0da2290892a46c051652001493bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378440"
---
# <a name="creating-and-repairing-stages"></a><span data-ttu-id="9019f-102">作成と修復段階</span><span class="sxs-lookup"><span data-stu-id="9019f-102">Creating and Repairing Stages</span></span>
<span data-ttu-id="9019f-103">作成または修復のステージは、任意のワークフローの最初のステージ、として定義されている機能を持つロールの作成、または修復します。</span><span class="sxs-lookup"><span data-stu-id="9019f-103">The first stage in any workflow can be either a Create or Repair stage, that is, roles that have a capability defined as create or repair.</span></span> <span data-ttu-id="9019f-104">失敗したメッセージとして BizTalk メッセージ ボックスから、メッセージの生成元または[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが経由でメッセージを手動で作成、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。</span><span class="sxs-lookup"><span data-stu-id="9019f-104">The message originates from the BizTalk MessageBox as a failed message or an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user manually creates a message through the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms.</span></span>  
  
 <span data-ttu-id="9019f-105">メッセージの最初のデジタル署名者は、元のメッセージの作成者または修理会社に自分のデジタル署名を追加、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]作成またはメッセージを修復した後のフォームです。</span><span class="sxs-lookup"><span data-stu-id="9019f-105">The original message creator or repairer is the first digital signer of the message, and adds his or her digital signature to the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form after creating or repairing the message.</span></span> <span data-ttu-id="9019f-106">この最初の署名は、メッセージの作成者または修理会社の身元を証明だけでなく、また現在の状態でメッセージの内容をロックします。</span><span class="sxs-lookup"><span data-stu-id="9019f-106">This first signature not only proves the identity of the message creator or repairer, but also locks the contents of the message in its current state.</span></span> <span data-ttu-id="9019f-107">最初のサインインした後、メッセージが変更される場合、デジタル署名のスタックが壊れていると、フォーム上のデジタル署名が有効であることを通知する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9019f-107">If the message is altered after the first signing, the digital signature stack is broken and warnings are shown to the user stating that the digital signatures on the form are invalid.</span></span>