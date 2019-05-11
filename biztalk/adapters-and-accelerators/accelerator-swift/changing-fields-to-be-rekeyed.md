---
title: 変更するフィールドの変更 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- rekeyed fields
- Message Repair and New Submission, modifying fields
- Message Repair and New Submission, rekeyed fields
ms.assetid: aaf353f7-0e43-403e-b72a-88e5dd07f4ac
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0468a692ecb7099920fca1c4714feb8ee9c1dfce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378903"
---
# <a name="changing-fields-to-be-rekeyed"></a><span data-ttu-id="57f96-102">変更するフィールドの変更</span><span class="sxs-lookup"><span data-stu-id="57f96-102">Changing Fields to Be Rekeyed</span></span>
<span data-ttu-id="57f96-103">メッセージの修復ワークフローの検証手順で[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]検証ツールの再入力すると、または、そのデータを更新する必要がありますように、フィールドの数からデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="57f96-103">In the verification step of a message repair workflow, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] removes the data from a number of fields so that the verifier must re-enter, or rekey, that data.</span></span> <span data-ttu-id="57f96-104">RekeyVerify 内のフィールドをカスタマイズする[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57f96-104">You can customize which fields in the RekeyVerify [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form need to be rekeyed.</span></span> <span data-ttu-id="57f96-105">ある MrsrXpathConfig.xml ファイルでこれを行う、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR フォルダー。</span><span class="sxs-lookup"><span data-stu-id="57f96-105">You do so in the MrsrXpathConfig.xml file, which is located in the \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR folder.</span></span>  
  
 <span data-ttu-id="57f96-106">MrsrXpathConfig.xml ファイルには、一連処理メッセージの種類のノードにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57f96-106">The MrsrXpathConfig.xml file contains a series of nodes for the message type processed.</span></span> <span data-ttu-id="57f96-107">各メッセージの種類のノードには、一連フィールドごとに 1 つのフィールド ノードにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57f96-107">Each message-type node contains a series of field nodes, one for each field.</span></span> <span data-ttu-id="57f96-108">MrsrXpathConfig.xml をメモ帳などのテキスト エディターで開いてを追加または削除によって変更するフィールドを変更することができます、\<パス\>フィールドのノード。</span><span class="sxs-lookup"><span data-stu-id="57f96-108">You can change the fields to be rekeyed by opening MrsrXpathConfig.xml in a text editor, such as Notepad, and adding or removing a \<path\> node for the field.</span></span>  
  
 <span data-ttu-id="57f96-109">\<パス\>ノードには、メッセージの種類と、フィールドのパスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57f96-109">The \<path\> node contains paths for the message type and the field.</span></span> <span data-ttu-id="57f96-110">たとえば、MT103 メッセージの入力アプリケーション ヘッダー ブロックの宛先パスのエントリは、次に示します。</span><span class="sxs-lookup"><span data-stu-id="57f96-110">For example, the entry for the Destination Path in the Input Application Header Block of an MT103 message is the following:</span></span>  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 <span data-ttu-id="57f96-111">コピーおよび貼り付けて既存のエントリと関連するパスを変更することによって変更する新しいフィールドを追加する最も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="57f96-111">It is easiest to add a new field to be rekeyed by copying and then pasting an existing entry, and then changing the relevant paths.</span></span> <span data-ttu-id="57f96-112">たとえば、MT103 メッセージの値の日付銀行間決済金額 32 a のセクションでは、Date フィールドのキー更新を強制するには、上記のコードを次の 3 つの置換をください。</span><span class="sxs-lookup"><span data-stu-id="57f96-112">For example, to force rekey of the Date field in the Value Date Currency Interbank Settled Amount 32A section of an MT103 message, make the following three replacements to the preceding code.</span></span> <span data-ttu-id="57f96-113">コードの残りの部分は同じです。</span><span class="sxs-lookup"><span data-stu-id="57f96-113">The rest of the code remains the same.</span></span>  
  
|<span data-ttu-id="57f96-114">これで置き換えます</span><span class="sxs-lookup"><span data-stu-id="57f96-114">Replace this</span></span>|<span data-ttu-id="57f96-115">こっちと</span><span class="sxs-lookup"><span data-stu-id="57f96-115">With this</span></span>|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 <span data-ttu-id="57f96-116">キー フィールドの更新の詳細については、次を参照してください。 [Message Repair and New Submission で特別な処理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)します。</span><span class="sxs-lookup"><span data-stu-id="57f96-116">For more information about rekeying fields, see [Special Processing in Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md).</span></span>