---
title: 時間検証のためのオフセットを設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, validating
- validating, amounts
- amounts, offsets
- offsets
ms.assetid: 39d5510c-52e6-4fd9-9632-582b508f04d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cfae474407daa7dd3c0b95db3fed076a581cf1c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961256"
---
# <a name="setting-offsets-for-amount-validation"></a><span data-ttu-id="48d46-102">時間検証のためのオフセットを設定します。</span><span class="sxs-lookup"><span data-stu-id="48d46-102">Setting Offsets for Amount Validation</span></span>
<span data-ttu-id="48d46-103">メッセージ型 MT102、MT103、や MT103PLUS 金額のフィールドの使用に関する規則は、それぞれの検証ポリシーのルールによって検証されます。</span><span class="sxs-lookup"><span data-stu-id="48d46-103">The usage rules for Amount fields in message types MT102, MT103, and MT103PLUS are validated by rules in their respective validation policies.</span></span> <span data-ttu-id="48d46-104">金額のフィールドは、厳密に一致することができます。 または金額の範囲内であることを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="48d46-104">The Amount fields can be matched exactly or can be validated to be within a range of amounts.</span></span>  
  
 <span data-ttu-id="48d46-105">範囲内での検証を有効にするには、関連する検証ポリシーでメソッドの呼び出しでオフセットの割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="48d46-105">To enable validation within a range, you specify an offset percentage in the method call in the relevant validation policy.</span></span> <span data-ttu-id="48d46-106">フィールドに設定した金額が 100、オフセットの割合が 10% 場合は、たとえば、有効な金額では、110、包括的に 90 から任意の値になります。</span><span class="sxs-lookup"><span data-stu-id="48d46-106">For example, if the amount that you set for the field is 100, and the offset percentage is 10 percent, a valid amount would be any value from 90 to 110, inclusive.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="48d46-107">MT102、MT102PLUS、および MT103 メッセージの種類には、このサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="48d46-107"> provides this support for the MT102, MT102PLUS, and MT103 message types.</span></span>  
  
 <span data-ttu-id="48d46-108">オフセットの割合がいずれかで指定された、 **IsValidSettlementAmount**または**IsValidInterbankSettledAmount**検証ポリシー内のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="48d46-108">The offset percentage is specified in either the **IsValidSettlementAmount** or **IsValidInterbankSettledAmount** method in the validation policy.</span></span> <span data-ttu-id="48d46-109">**IsValidSettlementAmount** MT102 および MT102PLUS メッセージの量のフィールドの使用量のルールを実装するメソッド。</span><span class="sxs-lookup"><span data-stu-id="48d46-109">The **IsValidSettlementAmount** method implements the usage rule for Amount fields of MT102 and MT102PLUS messages.</span></span> <span data-ttu-id="48d46-110">**IsValidInterbankSettledAmount** MT103 メッセージの量のフィールドの使用量のルールを実装するメソッド。</span><span class="sxs-lookup"><span data-stu-id="48d46-110">The **IsValidInterbankSettledAmount** method implements the usage rule for Amount fields of MT103 messages.</span></span> <span data-ttu-id="48d46-111">オフセットの割合を指定するには、これらのメソッドのいずれかの 10 番目の引数である OffsetPercent 引数にします。</span><span class="sxs-lookup"><span data-stu-id="48d46-111">You specify the offset percentage in the OffsetPercent argument, which is the tenth argument of either of those methods.</span></span>  
  
 <span data-ttu-id="48d46-112">オフセットのパーセントは設定すると、次のフィールドに適用されます。</span><span class="sxs-lookup"><span data-stu-id="48d46-112">When set, the percentage offset applies to the following fields:</span></span>  
  
|<span data-ttu-id="48d46-113">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="48d46-113">Message type</span></span>|<span data-ttu-id="48d46-114">フィールドのオフセットを使用して検証</span><span class="sxs-lookup"><span data-stu-id="48d46-114">Fields validated with offsets</span></span>|  
|------------------|-----------------------------------|  
|<span data-ttu-id="48d46-115">MT102 または MT102PLUS</span><span class="sxs-lookup"><span data-stu-id="48d46-115">MT102 or MT102PLUS</span></span>|<span data-ttu-id="48d46-116">32</span><span class="sxs-lookup"><span data-stu-id="48d46-116">32</span></span><br /><br /> <span data-ttu-id="48d46-117">33B</span><span class="sxs-lookup"><span data-stu-id="48d46-117">33B</span></span>|  
|<span data-ttu-id="48d46-118">MT103</span><span class="sxs-lookup"><span data-stu-id="48d46-118">MT103</span></span>|<span data-ttu-id="48d46-119">シーケンス C、19</span><span class="sxs-lookup"><span data-stu-id="48d46-119">19, Sequence C</span></span><br /><br /> <span data-ttu-id="48d46-120">31A、シーケンス C</span><span class="sxs-lookup"><span data-stu-id="48d46-120">31A, Sequence C</span></span><br /><br /> <span data-ttu-id="48d46-121">72 G</span><span class="sxs-lookup"><span data-stu-id="48d46-121">72G</span></span>|  
  
### <a name="to-set-an-offset-percentage"></a><span data-ttu-id="48d46-122">オフセットの割合を設定するには</span><span class="sxs-lookup"><span data-stu-id="48d46-122">To set an offset percentage</span></span>  
  
1.  <span data-ttu-id="48d46-123">メモ帳などのテキスト エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="48d46-123">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="48d46-124">エディターでは、オフセットの割合を設定するメッセージの検証ポリシーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="48d46-124">In the editor, browse to the location of the message validation policy in which you want to set an offset percentage.</span></span> <span data-ttu-id="48d46-125">たとえば、メッセージ検証ポリシー用あります MT103 メッセージの種類、MT103_Validation_Policy.xml で*\<ドライブ\>*: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Category 1\MT103 です。</span><span class="sxs-lookup"><span data-stu-id="48d46-125">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span> <span data-ttu-id="48d46-126">検証ポリシーを開きます。</span><span class="sxs-lookup"><span data-stu-id="48d46-126">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="48d46-127">ポリシーで IsValidSettlementAmount で MT102 および MT102PLUS メッセージまたは IsValidInterbankSettledAmount MT103 メッセージ検索します。</span><span class="sxs-lookup"><span data-stu-id="48d46-127">In the policy, search on IsValidSettlementAmount for MT102 and MT102PLUS messages or IsValidInterbankSettledAmount for MT103 messages.</span></span>  
  
4.  <span data-ttu-id="48d46-128">10 番目の引数には、カウント ダウンします。</span><span class="sxs-lookup"><span data-stu-id="48d46-128">Count down to the tenth argument.</span></span> <span data-ttu-id="48d46-129">引数のオフセットの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="48d46-129">Enter the percentage of the offset in the argument.</span></span>  
  
5.  <span data-ttu-id="48d46-130">ファイルを保存し、エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="48d46-130">Save the file, and then close the editor.</span></span>