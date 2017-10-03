---
title: "作成と修復段階 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stages, repair
- stages, create
ms.assetid: 07d7ce7b-ed15-40a7-9c85-280a1d38985b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb87112775b9664badf319796e1a6243cf6eb082
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-repairing-stages"></a><span data-ttu-id="6e8ee-102">作成とステージの修復</span><span class="sxs-lookup"><span data-stu-id="6e8ee-102">Creating and Repairing Stages</span></span>
<span data-ttu-id="6e8ee-103">任意のワークフローの最初のステージは、Create または修復の段階、として定義されている機能を持つロールの作成は、または修復します。</span><span class="sxs-lookup"><span data-stu-id="6e8ee-103">The first stage in any workflow can be either a Create or Repair stage, that is, roles that have a capability defined as create or repair.</span></span> <span data-ttu-id="6e8ee-104">失敗したメッセージとして BizTalk メッセージ ボックスから、メッセージの生成元または[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが経由でメッセージを手動で作成、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。</span><span class="sxs-lookup"><span data-stu-id="6e8ee-104">The message originates from the BizTalk MessageBox as a failed message or an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user manually creates a message through the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms.</span></span>  
  
 <span data-ttu-id="6e8ee-105">メッセージの最初のデジタル署名者は、元のメッセージの作成者または修理会社に自分のデジタル署名を追加、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]作成またはメッセージを修復した後のフォームです。</span><span class="sxs-lookup"><span data-stu-id="6e8ee-105">The original message creator or repairer is the first digital signer of the message, and adds his or her digital signature to the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form after creating or repairing the message.</span></span> <span data-ttu-id="6e8ee-106">この最初の署名は、メッセージの作成者または修理会社の身元を証明だけでなく、また現在の状態でメッセージの内容をロックします。</span><span class="sxs-lookup"><span data-stu-id="6e8ee-106">This first signature not only proves the identity of the message creator or repairer, but also locks the contents of the message in its current state.</span></span> <span data-ttu-id="6e8ee-107">メッセージは、最初の署名後に変更する場合、デジタル署名スタックが壊れていると、フォーム上のデジタル署名が無効であることを示すユーザーに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e8ee-107">If the message is altered after the first signing, the digital signature stack is broken and warnings are shown to the user stating that the digital signatures on the form are invalid.</span></span>