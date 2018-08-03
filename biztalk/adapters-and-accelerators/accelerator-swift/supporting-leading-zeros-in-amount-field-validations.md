---
title: 先行する量フィールドの検証時にゼロをサポートする |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, amount fields
- amounts, leading zeros
- validating, amount fields
ms.assetid: 7c202422-019f-43da-9c2a-4b9fdf0b2859
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3559b63ec7588fa2d7451779947a476cf19b7bf0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961368"
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a><span data-ttu-id="bf5c8-102">先行する量フィールドの検証時にゼロをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-102">Supporting Leading Zeros in Amount Field Validations</span></span>
<span data-ttu-id="bf5c8-103">一部のメッセージ型の検証ポリシーは、金額のフィールドの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-103">The validation policies of some message types perform validations on Amount fields.</span></span> <span data-ttu-id="bf5c8-104">金額フィールドには先行ゼロを有効にするには、メッセージの種類の検証ポリシーを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-104">To enable leading zeros in Amount fields, you must edit the validation policy for the message type.</span></span> <span data-ttu-id="bf5c8-105">既定の検証ポリシーの新しいバージョンを作成して、ビジネス ルール作成ツールの引数を編集またはポリシーを展開する前に、のテキスト エディターで手動で既定のポリシーを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-105">You can create a new version of the default validation policy, and edit the argument in the Business Rule Composer, or you can edit the default policy manually in a text editor before the policy is deployed.</span></span>  
  
 <span data-ttu-id="bf5c8-106">次の表は、有効にするにまたは先行ゼロを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-106">The following table lists the methods that enable or disable leading zeros.</span></span> <span data-ttu-id="bf5c8-107">メソッドに設定する必要がありますを指定する引数の序数も示します。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-107">The table also indicates the ordinal number of the argument that you need to set in the method.</span></span> <span data-ttu-id="bf5c8-108">先行ゼロを有効にする場合は true または false に設定すると、それらを無効にするのを設定します。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-108">Set it to True to enable leading zeros, or to False to disable them.</span></span>  
  
|<span data-ttu-id="bf5c8-109">方法</span><span class="sxs-lookup"><span data-stu-id="bf5c8-109">Method</span></span>|<span data-ttu-id="bf5c8-110">引数の数</span><span class="sxs-lookup"><span data-stu-id="bf5c8-110">Argument number</span></span>|  
|------------|---------------------|  
|<span data-ttu-id="bf5c8-111">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="bf5c8-111">**CheckValidAmount**</span></span>|<span data-ttu-id="bf5c8-112">6</span><span class="sxs-lookup"><span data-stu-id="bf5c8-112">6</span></span>|  
|<span data-ttu-id="bf5c8-113">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="bf5c8-113">**CheckCurrencyAmount**</span></span>|<span data-ttu-id="bf5c8-114">4</span><span class="sxs-lookup"><span data-stu-id="bf5c8-114">4</span></span>|  
|<span data-ttu-id="bf5c8-115">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="bf5c8-115">**CheckValidSignCurrencyAmount**</span></span>|<span data-ttu-id="bf5c8-116">3</span><span class="sxs-lookup"><span data-stu-id="bf5c8-116">3</span></span>|  
|<span data-ttu-id="bf5c8-117">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="bf5c8-117">**CheckValidSignDateCurrencyAmount**</span></span>|<span data-ttu-id="bf5c8-118">4</span><span class="sxs-lookup"><span data-stu-id="bf5c8-118">4</span></span>|  
|<span data-ttu-id="bf5c8-119">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="bf5c8-119">**IsValidTransactionDetailsCurrencyAmount**</span></span>|<span data-ttu-id="bf5c8-120">4</span><span class="sxs-lookup"><span data-stu-id="bf5c8-120">4</span></span>|  
  
 <span data-ttu-id="bf5c8-121">上記の表の各メソッドは、1 つまたは複数のメッセージ検証ポリシーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-121">Each method in the preceding table is contained in one or more message validation policies.</span></span> <span data-ttu-id="bf5c8-122">ポリシーで、引数を設定するには、そのポリシーがあるかどうかを確認するメソッドの名前で検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-122">To set the argument in a policy, you must search on the method name to verify whether the policy contains it.</span></span> <span data-ttu-id="bf5c8-123">メソッドは、メッセージのポリシーに複数回を表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-123">A method may appear multiple times in a message's policy.</span></span>  
  
### <a name="to-enable-or-disable-leading-zeros"></a><span data-ttu-id="bf5c8-124">有効にするにまたは先行ゼロを無効にするには</span><span class="sxs-lookup"><span data-stu-id="bf5c8-124">To enable or disable leading zeros</span></span>  
  
1.  <span data-ttu-id="bf5c8-125">メモ帳などのテキスト エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-125">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="bf5c8-126">エディターで、有効にするにまたは先行ゼロを無効にするメッセージの検証ポリシーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-126">In the editor, browse to the location of the message validation policy in which you want to enable or disable leading zeros.</span></span> <span data-ttu-id="bf5c8-127">たとえば、メッセージ検証ポリシー用あります MT103 メッセージの種類、MT103_Validation_Policy.xml で*\<ドライブ\>*:/プログラム ファイル/BizTalk Accelerator for SWIFT/SWIFT メッセージ/カテゴリ 1/MT103 です。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-127">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:/Program Files/Microsoft BizTalk Accelerator for SWIFT/SWIFT Messages/Category 1/MT103.</span></span> <span data-ttu-id="bf5c8-128">検証ポリシーを開きます。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-128">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="bf5c8-129">ポリシーでの検索、 **CheckValidAmount**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-129">In the policy, search on the **CheckValidAmount** method.</span></span>  
  
4.  <span data-ttu-id="bf5c8-130">メソッドを検索する場合、適切な引数をカウント ダウンします。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-130">If you find the method, count down to the appropriate argument.</span></span> <span data-ttu-id="bf5c8-131">たとえば、 **CheckValidAmount**メソッド、6 番目の引数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-131">For example, for the **CheckValidAmount** method, count down to the sixth argument.</span></span> <span data-ttu-id="bf5c8-132">引数に設定**True**を先頭にゼロまたはそれらを無効にする場合は False を有効にします。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-132">Set the argument to **True** to enable leading zeros or False to disable them.</span></span>  
  
5.  <span data-ttu-id="bf5c8-133">上記の表の各メソッドを手順 3. および 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-133">Repeat steps 3 and 4 for each method in the preceding table.</span></span>  
  
6.  <span data-ttu-id="bf5c8-134">ファイルを保存し、エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-134">Save the file, and then close the editor.</span></span>