---
title: 量のフィールドの検証時に先頭のゼロをサポートしている |Microsoft Docs
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
ms.openlocfilehash: e68cb3f776fd177bfaf437c6ae84b3e1da36f084
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529796"
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a><span data-ttu-id="29c97-102">量のフィールドの検証時に先頭のゼロをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="29c97-102">Supporting Leading Zeros in Amount Field Validations</span></span>
<span data-ttu-id="29c97-103">いくつかのメッセージの検証ポリシーは、高のフィールドの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="29c97-103">The validation policies of some message types perform validations on Amount fields.</span></span> <span data-ttu-id="29c97-104">量のフィールドには先行ゼロを有効にするには、メッセージの種類の検証ポリシーを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c97-104">To enable leading zeros in Amount fields, you must edit the validation policy for the message type.</span></span> <span data-ttu-id="29c97-105">既定の検証ポリシーの新しいバージョンを作成し、ビジネス ルール作成ツールの引数を編集またはポリシーを展開する前に、テキスト エディターで手動で既定のポリシーを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="29c97-105">You can create a new version of the default validation policy, and edit the argument in the Business Rule Composer, or you can edit the default policy manually in a text editor before the policy is deployed.</span></span>  
  
 <span data-ttu-id="29c97-106">次の表では、有効または先行ゼロを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29c97-106">The following table lists the methods that enable or disable leading zeros.</span></span> <span data-ttu-id="29c97-107">メソッドに設定する必要のある引数の序数も示します。</span><span class="sxs-lookup"><span data-stu-id="29c97-107">The table also indicates the ordinal number of the argument that you need to set in the method.</span></span> <span data-ttu-id="29c97-108">先行するゼロを有効にする場合は true または False を無効にするを設定します。</span><span class="sxs-lookup"><span data-stu-id="29c97-108">Set it to True to enable leading zeros, or to False to disable them.</span></span>  
  
|<span data-ttu-id="29c97-109">方法</span><span class="sxs-lookup"><span data-stu-id="29c97-109">Method</span></span>|<span data-ttu-id="29c97-110">引数の数</span><span class="sxs-lookup"><span data-stu-id="29c97-110">Argument number</span></span>|  
|------------|---------------------|  
|<span data-ttu-id="29c97-111">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="29c97-111">**CheckValidAmount**</span></span>|<span data-ttu-id="29c97-112">6</span><span class="sxs-lookup"><span data-stu-id="29c97-112">6</span></span>|  
|<span data-ttu-id="29c97-113">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="29c97-113">**CheckCurrencyAmount**</span></span>|<span data-ttu-id="29c97-114">4</span><span class="sxs-lookup"><span data-stu-id="29c97-114">4</span></span>|  
|<span data-ttu-id="29c97-115">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="29c97-115">**CheckValidSignCurrencyAmount**</span></span>|<span data-ttu-id="29c97-116">3</span><span class="sxs-lookup"><span data-stu-id="29c97-116">3</span></span>|  
|<span data-ttu-id="29c97-117">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="29c97-117">**CheckValidSignDateCurrencyAmount**</span></span>|<span data-ttu-id="29c97-118">4</span><span class="sxs-lookup"><span data-stu-id="29c97-118">4</span></span>|  
|<span data-ttu-id="29c97-119">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="29c97-119">**IsValidTransactionDetailsCurrencyAmount**</span></span>|<span data-ttu-id="29c97-120">4</span><span class="sxs-lookup"><span data-stu-id="29c97-120">4</span></span>|  
  
 <span data-ttu-id="29c97-121">上記の表の各メソッドは、1 つまたは複数のメッセージの検証ポリシーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="29c97-121">Each method in the preceding table is contained in one or more message validation policies.</span></span> <span data-ttu-id="29c97-122">ポリシーで、引数を設定するには、そのポリシーに含まれているかどうかを確認するメソッド名で検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c97-122">To set the argument in a policy, you must search on the method name to verify whether the policy contains it.</span></span> <span data-ttu-id="29c97-123">メソッドは、メッセージのポリシーで複数回を表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="29c97-123">A method may appear multiple times in a message's policy.</span></span>  
  
### <a name="to-enable-or-disable-leading-zeros"></a><span data-ttu-id="29c97-124">有効または先行ゼロを無効にするには</span><span class="sxs-lookup"><span data-stu-id="29c97-124">To enable or disable leading zeros</span></span>  
  
1.  <span data-ttu-id="29c97-125">メモ帳などのテキスト エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="29c97-125">Open a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="29c97-126">エディターでは、有効または先行ゼロを無効にするメッセージの検証ポリシーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="29c97-126">In the editor, browse to the location of the message validation policy in which you want to enable or disable leading zeros.</span></span> <span data-ttu-id="29c97-127">たとえば、見つかりますメッセージの検証ポリシー MT103_Validation_Policy.xml、MT103 メッセージの種類で*\<ドライブ\>*:/SWIFT/SWIFT メッセージのプログラム ファイルと Microsoft BizTalk Accelerator/カテゴリ 1/MT103 します。</span><span class="sxs-lookup"><span data-stu-id="29c97-127">For example, you can find the message validation policy for the MT103 message type, MT103_Validation_Policy.xml, in *\<drive\>*:/Program Files/Microsoft BizTalk Accelerator for SWIFT/SWIFT Messages/Category 1/MT103.</span></span> <span data-ttu-id="29c97-128">検証ポリシーを開きます。</span><span class="sxs-lookup"><span data-stu-id="29c97-128">Open the validation policy.</span></span>  
  
3.  <span data-ttu-id="29c97-129">ポリシーでは、検索、 **CheckValidAmount**メソッド。</span><span class="sxs-lookup"><span data-stu-id="29c97-129">In the policy, search on the **CheckValidAmount** method.</span></span>  
  
4.  <span data-ttu-id="29c97-130">メソッドを検索する場合、適切な引数にカウント ダウンします。</span><span class="sxs-lookup"><span data-stu-id="29c97-130">If you find the method, count down to the appropriate argument.</span></span> <span data-ttu-id="29c97-131">たとえば、 **CheckValidAmount**メソッド、6 番目の引数までカウントします。</span><span class="sxs-lookup"><span data-stu-id="29c97-131">For example, for the **CheckValidAmount** method, count down to the sixth argument.</span></span> <span data-ttu-id="29c97-132">引数を設定**True**先頭のゼロまたは無効にする場合は False を有効にします。</span><span class="sxs-lookup"><span data-stu-id="29c97-132">Set the argument to **True** to enable leading zeros or False to disable them.</span></span>  
  
5.  <span data-ttu-id="29c97-133">前のテーブル内の各メソッドには、手順 3. および 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="29c97-133">Repeat steps 3 and 4 for each method in the preceding table.</span></span>  
  
6.  <span data-ttu-id="29c97-134">ファイルを保存し、エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="29c97-134">Save the file, and then close the editor.</span></span>