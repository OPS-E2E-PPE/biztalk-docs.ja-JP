---
title: キー更新の検証ステージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- rekey verification
- stages, rekey verification
ms.assetid: 8a2880b6-bb25-4af5-9f51-d0b090ca38c8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18f0d6acc7621ac50ef257c481d8ce7486ad74bf
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529988"
---
# <a name="rekey-verification-stage"></a><span data-ttu-id="54278-102">検証ステージの再入力します。</span><span class="sxs-lookup"><span data-stu-id="54278-102">Rekey Verification Stage</span></span>
<span data-ttu-id="54278-103">ステージがメッセージ修復のワークフローで発生したメッセージの修復と新しい送信メッセージの正確なコピーして、元のメッセージのコピーが保持されるキーを再入力の検証がの検証ツールの受信トレイに送信されるときに検証の再入力します。</span><span class="sxs-lookup"><span data-stu-id="54278-103">When a Rekey Verification stage occurs in the message repair workflow, a copy of the original message is maintained by Message Repair and New Submission and an exact copy of the message is sent to the verifier's inbox for rekey verification.</span></span> <span data-ttu-id="54278-104">キー更新の検証、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission の手動の再指定フィールドをクリアします。</span><span class="sxs-lookup"><span data-stu-id="54278-104">In rekey verification, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission clears specified fields for manual re-entry.</span></span>  
  
 <span data-ttu-id="54278-105">この概念は」で詳しく、 [Server ランタイム セキュリティ](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="54278-105">This concept is explained further in the [Server Runtime Security](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md) topic.</span></span> <span data-ttu-id="54278-106">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー鍵更新の検証段階に参加している必要があります手動で再入力をクリアされたフィールドにを通じて、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ([作成] または修復段階) から元のメッセージが正確に一致する値を形成します。</span><span class="sxs-lookup"><span data-stu-id="54278-106">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user participating in the Rekey Verification stage must manually re-enter into the cleared fields, through the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, values that exactly match those in the original message (from either the Create or Repair stage).</span></span> <span data-ttu-id="54278-107">検証ツールは、有効な証明書を持つメッセージに署名し、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="54278-107">The verifier then signs the message with a valid certificate and submits the message.</span></span>  
  
 <span data-ttu-id="54278-108">Rekeyed フィールドの値では、元のメッセージ フィールドを正確に一致しない場合、は、ワークフロー内のステージをリセット Message Repair and New Submission し、メッセージを修理会社の受信トレイに送信します。</span><span class="sxs-lookup"><span data-stu-id="54278-108">If the values of the rekeyed fields do not match the original message fields exactly, Message Repair and New Submission resets the stage in the workflow and sends the message back to the repairer's inbox.</span></span> <span data-ttu-id="54278-109">また、フィールドを変更した検証の署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="54278-109">It also validates the signature of the verifier who rekeyed the fields.</span></span> <span data-ttu-id="54278-110">検証ツールが検証されない場合は、検証の受信トレイに、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="54278-110">If the verifier is not validated, it sends the message back to the verifier's inbox.</span></span>