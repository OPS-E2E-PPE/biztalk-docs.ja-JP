---
title: 再生成するフィールドの変更 |Microsoft ドキュメント
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
ms.openlocfilehash: 04693bf4c4d441487a3ce38f886bc680b1db368b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964496"
---
# <a name="changing-fields-to-be-rekeyed"></a><span data-ttu-id="9ed9d-102">再生成するフィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-102">Changing Fields to Be Rekeyed</span></span>
<span data-ttu-id="9ed9d-103">メッセージの修復ワークフローの検証手順で[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ように、検証側は必要がありますを再入力したり鍵更新、そのデータ フィールドの数からそのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-103">In the verification step of a message repair workflow, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] removes the data from a number of fields so that the verifier must re-enter, or rekey, that data.</span></span> <span data-ttu-id="9ed9d-104">RekeyVerify 内のどのフィールドをカスタマイズする[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-104">You can customize which fields in the RekeyVerify [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form need to be rekeyed.</span></span> <span data-ttu-id="9ed9d-105">ある MrsrXpathConfig.xml ファイルで行う、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-105">You do so in the MrsrXpathConfig.xml file, which is located in the \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR folder.</span></span>  
  
 <span data-ttu-id="9ed9d-106">MrsrXpathConfig.xml ファイルには、一連処理されたメッセージの種類のノードにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-106">The MrsrXpathConfig.xml file contains a series of nodes for the message type processed.</span></span> <span data-ttu-id="9ed9d-107">メッセージの種類の各ノードには、一連フィールドごとに 1 つのフィールド ノードにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-107">Each message-type node contains a series of field nodes, one for each field.</span></span> <span data-ttu-id="9ed9d-108">メモ帳などのテキスト エディターで MrsrXpathConfig.xml を開いて、追加または削除して再生成するのにフィールドを変更することができます、\<パス\>フィールドのノードです。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-108">You can change the fields to be rekeyed by opening MrsrXpathConfig.xml in a text editor, such as Notepad, and adding or removing a \<path\> node for the field.</span></span>  
  
 <span data-ttu-id="9ed9d-109">\<パス\>ノードには、メッセージの種類と、フィールドのパスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-109">The \<path\> node contains paths for the message type and the field.</span></span> <span data-ttu-id="9ed9d-110">たとえば、MT103 メッセージの入力アプリケーション ヘッダー ブロック先のパスのエントリは、次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-110">For example, the entry for the Destination Path in the Input Application Header Block of an MT103 message is the following:</span></span>  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 <span data-ttu-id="9ed9d-111">方が簡単にコピーして貼り付けなくても、既存のエントリでは、関連するパスを変更することに再生成する新しいフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-111">It is easiest to add a new field to be rekeyed by copying and then pasting an existing entry, and then changing the relevant paths.</span></span> <span data-ttu-id="9ed9d-112">など、日付、日付通貨銀行間決済金額 32 a のセクションでフィールド MT103 メッセージのキー更新を強制するには、上記のコードを次の 3 つの置換を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-112">For example, to force rekey of the Date field in the Value Date Currency Interbank Settled Amount 32A section of an MT103 message, make the following three replacements to the preceding code.</span></span> <span data-ttu-id="9ed9d-113">コードの残りの部分は変わりません。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-113">The rest of the code remains the same.</span></span>  
  
|<span data-ttu-id="9ed9d-114">これで置き換えます</span><span class="sxs-lookup"><span data-stu-id="9ed9d-114">Replace this</span></span>|<span data-ttu-id="9ed9d-115">こっちと</span><span class="sxs-lookup"><span data-stu-id="9ed9d-115">With this</span></span>|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 <span data-ttu-id="9ed9d-116">フィールドのキー更新の詳細については、次を参照してください。 [Message Repair and New Submission の特別な処理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)です。</span><span class="sxs-lookup"><span data-stu-id="9ed9d-116">For more information about rekeying fields, see [Special Processing in Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md).</span></span>