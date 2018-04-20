---
title: 'シングル サインオン: イベント 10854 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8faed9d-5c7e-4b99-bcd9-ea5f670d5e72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42f9e9e761689b2ed21ec37acdbb8a63f1f88070
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="single-sign-on-event-10854"></a><span data-ttu-id="ebe89-102">シングル サインオン: イベント 10854</span><span class="sxs-lookup"><span data-stu-id="ebe89-102">Single Sign-On: Event 10854</span></span>
## <a name="details"></a><span data-ttu-id="ebe89-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ebe89-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ebe89-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ebe89-104">Product Name</span></span>|<span data-ttu-id="ebe89-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ebe89-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ebe89-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ebe89-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ebe89-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ebe89-107">Event ID</span></span>|<span data-ttu-id="ebe89-108">10854</span><span class="sxs-lookup"><span data-stu-id="ebe89-108">10854</span></span>|  
|<span data-ttu-id="ebe89-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ebe89-109">Event Source</span></span>|<span data-ttu-id="ebe89-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ebe89-110">ENTSSO</span></span>|  
|<span data-ttu-id="ebe89-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ebe89-111">Component</span></span>|<span data-ttu-id="ebe89-112">なし</span><span class="sxs-lookup"><span data-stu-id="ebe89-112">N/A</span></span>|  
|<span data-ttu-id="ebe89-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ebe89-113">Symbolic Name</span></span>|<span data-ttu-id="ebe89-114">ENTSSO_E_INVALID_STRING_FORMAT</span><span class="sxs-lookup"><span data-stu-id="ebe89-114">ENTSSO_E_INVALID_STRING_FORMAT</span></span>|  
|<span data-ttu-id="ebe89-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ebe89-115">Message Text</span></span>|<span data-ttu-id="ebe89-116">この関数の文字列形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="ebe89-116">The string format is incorrect for this function.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ebe89-117">説明</span><span class="sxs-lookup"><span data-stu-id="ebe89-117">Explanation</span></span>  
 <span data-ttu-id="ebe89-118">この関数の文字列形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="ebe89-118">The string format is incorrect for this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ebe89-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ebe89-119">User Action</span></span>  
 <span data-ttu-id="ebe89-120">パスワード文字列の適切な形式について以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="ebe89-120">Proper formatting for password strings is described below:</span></span>  
  
 <span data-ttu-id="ebe89-121">VT_BSTR 型プロパティ</span><span class="sxs-lookup"><span data-stu-id="ebe89-121">VT_BSTR type property</span></span>  
  
 <span data-ttu-id="ebe89-122">区切り文字は / (スラッシュ) です</span><span class="sxs-lookup"><span data-stu-id="ebe89-122">The delimiter is / (slash)</span></span>  
  
 <span data-ttu-id="ebe89-123">dc = 既定の状態 (操作なし - 何も行いません)</span><span class="sxs-lookup"><span data-stu-id="ebe89-123">dc = default case (no operation - do nothing)</span></span>  
  
 <span data-ttu-id="ebe89-124">例: dc/</span><span class="sxs-lookup"><span data-stu-id="ebe89-124">Example: dc/</span></span>  
  
 <span data-ttu-id="ebe89-125">(変更しません - "Cat" は "Cat" になります)</span><span class="sxs-lookup"><span data-stu-id="ebe89-125">(no change - 'Cat' to 'Cat')</span></span>  
  
 <span data-ttu-id="ebe89-126">uc = 大文字</span><span class="sxs-lookup"><span data-stu-id="ebe89-126">uc = upper case</span></span>  
  
 <span data-ttu-id="ebe89-127">例: uc/</span><span class="sxs-lookup"><span data-stu-id="ebe89-127">Example: uc/</span></span>  
  
 <span data-ttu-id="ebe89-128">(パスワードを大文字に変更します - "Cat" は "CAT" になります)</span><span class="sxs-lookup"><span data-stu-id="ebe89-128">(change password to upper case - 'Cat' to 'CAT')</span></span>  
  
 <span data-ttu-id="ebe89-129">lc = 小文字</span><span class="sxs-lookup"><span data-stu-id="ebe89-129">lc = lower case</span></span>  
  
 <span data-ttu-id="ebe89-130">例: lc/</span><span class="sxs-lookup"><span data-stu-id="ebe89-130">Example: lc/</span></span>  
  
 <span data-ttu-id="ebe89-131">(パスワードを小文字に変更します - "Cat" は "cat" になります)</span><span class="sxs-lookup"><span data-stu-id="ebe89-131">(change password to lower case - 'Cat' to 'cat')</span></span>  
  
 <span data-ttu-id="ebe89-132">rc = 文字を削除します - 続けて文字数と文字を指定します</span><span class="sxs-lookup"><span data-stu-id="ebe89-132">rc = remove chars - followed by count followed by chars</span></span>  
  
 <span data-ttu-id="ebe89-133">例: rc/2/#@/</span><span class="sxs-lookup"><span data-stu-id="ebe89-133">Example: rc/2/#@/</span></span>  
  
 <span data-ttu-id="ebe89-134">('#' 文字を削除し、' @' のパスワードから 'C@t#'"Ct"に)</span><span class="sxs-lookup"><span data-stu-id="ebe89-134">(remove the characters '#' and '@' from the password - 'C@t#' to 'Ct')</span></span>  
  
 <span data-ttu-id="ebe89-135">sc = 文字を置換します - 続けて文字数、置換前の文字、置換語の文字を指定します</span><span class="sxs-lookup"><span data-stu-id="ebe89-135">sc = substitute chars - followed by count followed by chars to replace followed by substitute chars</span></span>  
  
 <span data-ttu-id="ebe89-136">例: sc/3/abc/def/</span><span class="sxs-lookup"><span data-stu-id="ebe89-136">Example: sc/3/abc/def/</span></span>  
  
 <span data-ttu-id="ebe89-137">(パスワードから文字 "a"、"b"、"c" を削除し、"d"、"e"、"f" にそれぞれ置き換えます)</span><span class="sxs-lookup"><span data-stu-id="ebe89-137">(remove the characters 'a', 'b' and 'c' from the password and replace with 'd', 'e' and 'f' respectively)</span></span>  
  
 <span data-ttu-id="ebe89-138">("Cat" は "Cdt" になります)</span><span class="sxs-lookup"><span data-stu-id="ebe89-138">('Cat' to 'Cdt')</span></span>  
  
 <span data-ttu-id="ebe89-139">ps = 先頭に挿入します - 続けて文字数 (パスワードの最小長) と挿入する 1 文字を指定します</span><span class="sxs-lookup"><span data-stu-id="ebe89-139">ps = pad from start - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="ebe89-140">例: ps/8/#/</span><span class="sxs-lookup"><span data-stu-id="ebe89-140">Example: ps/8/#/</span></span>  
  
 <span data-ttu-id="ebe89-141">(パスワードの長さが 8 文字以上でない場合、全体が 8 文字になるまで、文字列の先頭に文字 "#" を挿入します)</span><span class="sxs-lookup"><span data-stu-id="ebe89-141">(if the password is not at least 8 chars in length then pad from the start with the character '#' until there are 8 chars total)</span></span>  
  
 <span data-ttu-id="ebe89-142">("Cat" は "#####Cat" になります)</span><span class="sxs-lookup"><span data-stu-id="ebe89-142">('Cat' to '#####Cat')</span></span>  
  
 <span data-ttu-id="ebe89-143">pe = 末尾に挿入します - 続けて文字数 (パスワードの最小長) と挿入する 1 文字を指定します</span><span class="sxs-lookup"><span data-stu-id="ebe89-143">pe = pad from end - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="ebe89-144">例: pe/10/$/</span><span class="sxs-lookup"><span data-stu-id="ebe89-144">Example: pe/10/$/</span></span>  
  
 <span data-ttu-id="ebe89-145">(パスワードの長さが 10 文字以上でない場合、全体が 10 文字になるまで、文字列の末尾に文字 "$" を挿入します)</span><span class="sxs-lookup"><span data-stu-id="ebe89-145">(if the password is not at least 10 chars in length then pad to the end with the character '$' until there are 10 chars total)</span></span>  
  
 <span data-ttu-id="ebe89-146">("Cat"になります $$$ ')</span><span class="sxs-lookup"><span data-stu-id="ebe89-146">('Cat' to 'Cat$$$$$$$')</span></span>  
  
 <span data-ttu-id="ebe89-147">tr = 切り捨てます - 文字列の長さを制限します - 続けて文字数を指定します</span><span class="sxs-lookup"><span data-stu-id="ebe89-147">tr = truncate - limit length of string - followed by count</span></span>  
  
 <span data-ttu-id="ebe89-148">例: tr/11/</span><span class="sxs-lookup"><span data-stu-id="ebe89-148">Example: tr/11/</span></span>  
  
 <span data-ttu-id="ebe89-149">("Cat123456789" は "Cat12345678" になります)</span><span class="sxs-lookup"><span data-stu-id="ebe89-149">('Cat123456789' to 'Cat12345678');</span></span>  
  
 <span data-ttu-id="ebe89-150">トークンは文字列内での順序で処理されます。</span><span class="sxs-lookup"><span data-stu-id="ebe89-150">The tokens are processed in their order in the string.</span></span>  
  
 <span data-ttu-id="ebe89-151">例:</span><span class="sxs-lookup"><span data-stu-id="ebe89-151">Example:</span></span>  
  
 <span data-ttu-id="ebe89-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span><span class="sxs-lookup"><span data-stu-id="ebe89-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span></span>