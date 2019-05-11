---
title: シングル サインオン:イベント 10854 |Microsoft Docs
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
ms.openlocfilehash: 14d15f5f4bf2a3347b87ef624366177be63672c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306690"
---
# <a name="single-sign-on-event-10854"></a><span data-ttu-id="1246d-102">シングル サインオン:イベント 10854</span><span class="sxs-lookup"><span data-stu-id="1246d-102">Single Sign-On: Event 10854</span></span>
## <a name="details"></a><span data-ttu-id="1246d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1246d-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="1246d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1246d-104">Product Name</span></span>   |                 <span data-ttu-id="1246d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1246d-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="1246d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1246d-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="1246d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1246d-107">Event ID</span></span>     |                           <span data-ttu-id="1246d-108">10854</span><span class="sxs-lookup"><span data-stu-id="1246d-108">10854</span></span>                            |
|  <span data-ttu-id="1246d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1246d-109">Event Source</span></span>   |                           <span data-ttu-id="1246d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1246d-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="1246d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1246d-111">Component</span></span>    |                            <span data-ttu-id="1246d-112">なし</span><span class="sxs-lookup"><span data-stu-id="1246d-112">N/A</span></span>                             |
|  <span data-ttu-id="1246d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1246d-113">Symbolic Name</span></span>  |               <span data-ttu-id="1246d-114">ENTSSO_E_INVALID_STRING_FORMAT</span><span class="sxs-lookup"><span data-stu-id="1246d-114">ENTSSO_E_INVALID_STRING_FORMAT</span></span>               |
|  <span data-ttu-id="1246d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1246d-115">Message Text</span></span>   |     <span data-ttu-id="1246d-116">この関数の文字列の形式が正しくないです。</span><span class="sxs-lookup"><span data-stu-id="1246d-116">The string format is incorrect for this function.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="1246d-117">説明</span><span class="sxs-lookup"><span data-stu-id="1246d-117">Explanation</span></span>  
 <span data-ttu-id="1246d-118">この関数の文字列の形式が正しくないです。</span><span class="sxs-lookup"><span data-stu-id="1246d-118">The string format is incorrect for this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1246d-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1246d-119">User Action</span></span>  
 <span data-ttu-id="1246d-120">次のとおり、パスワードの文字列の適切な形式します。</span><span class="sxs-lookup"><span data-stu-id="1246d-120">Proper formatting for password strings is described below:</span></span>  
  
 <span data-ttu-id="1246d-121">VT_BSTR 型プロパティ</span><span class="sxs-lookup"><span data-stu-id="1246d-121">VT_BSTR type property</span></span>  
  
 <span data-ttu-id="1246d-122">区切り記号は/(スラッシュ)</span><span class="sxs-lookup"><span data-stu-id="1246d-122">The delimiter is / (slash)</span></span>  
  
 <span data-ttu-id="1246d-123">dc = 既定のケース (操作なし - 何もしない)</span><span class="sxs-lookup"><span data-stu-id="1246d-123">dc = default case (no operation - do nothing)</span></span>  
  
 <span data-ttu-id="1246d-124">例: dc/</span><span class="sxs-lookup"><span data-stu-id="1246d-124">Example: dc/</span></span>  
  
 <span data-ttu-id="1246d-125">(変更なし -"Cat"は"Cat"に)</span><span class="sxs-lookup"><span data-stu-id="1246d-125">(no change - 'Cat' to 'Cat')</span></span>  
  
 <span data-ttu-id="1246d-126">uc = 大文字</span><span class="sxs-lookup"><span data-stu-id="1246d-126">uc = upper case</span></span>  
  
 <span data-ttu-id="1246d-127">例: uc/</span><span class="sxs-lookup"><span data-stu-id="1246d-127">Example: uc/</span></span>  
  
 <span data-ttu-id="1246d-128">(パスワードを大文字に変換 -"Cat"は"CAT"に変更します)</span><span class="sxs-lookup"><span data-stu-id="1246d-128">(change password to upper case - 'Cat' to 'CAT')</span></span>  
  
 <span data-ttu-id="1246d-129">lc = 小文字</span><span class="sxs-lookup"><span data-stu-id="1246d-129">lc = lower case</span></span>  
  
 <span data-ttu-id="1246d-130">例: lc/</span><span class="sxs-lookup"><span data-stu-id="1246d-130">Example: lc/</span></span>  
  
 <span data-ttu-id="1246d-131">(大文字と小文字の-"Cat"は"cat"にするパスワードを変更する)</span><span class="sxs-lookup"><span data-stu-id="1246d-131">(change password to lower case - 'Cat' to 'cat')</span></span>  
  
 <span data-ttu-id="1246d-132">rc = 文字を削除します-続けて文字数</span><span class="sxs-lookup"><span data-stu-id="1246d-132">rc = remove chars - followed by count followed by chars</span></span>  
  
 <span data-ttu-id="1246d-133">例: rc/2/#@/</span><span class="sxs-lookup"><span data-stu-id="1246d-133">Example: rc/2/#@/</span></span>  
  
 <span data-ttu-id="1246d-134">('#' 文字を削除し、' @' からパスワード - 'C@t#' ct)</span><span class="sxs-lookup"><span data-stu-id="1246d-134">(remove the characters '#' and '@' from the password - 'C@t#' to 'Ct')</span></span>  
  
 <span data-ttu-id="1246d-135">sc = 文字に置換する文字数を続けての代替文字が続く代替</span><span class="sxs-lookup"><span data-stu-id="1246d-135">sc = substitute chars - followed by count followed by chars to replace followed by substitute chars</span></span>  
  
 <span data-ttu-id="1246d-136">例: sc/3/abc/def/</span><span class="sxs-lookup"><span data-stu-id="1246d-136">Example: sc/3/abc/def/</span></span>  
  
 <span data-ttu-id="1246d-137">(文字 'a'、'b' を削除しでのパスワードと置換から ' c' が '、'e' と 'f' それぞれ)</span><span class="sxs-lookup"><span data-stu-id="1246d-137">(remove the characters 'a', 'b' and 'c' from the password and replace with 'd', 'e' and 'f' respectively)</span></span>  
  
 <span data-ttu-id="1246d-138">("Cat"Cdt を)</span><span class="sxs-lookup"><span data-stu-id="1246d-138">('Cat' to 'Cdt')</span></span>  
  
 <span data-ttu-id="1246d-139">ps = 先頭に挿入の数 (パスワードの最小長) を挿入する 1 文字の後に</span><span class="sxs-lookup"><span data-stu-id="1246d-139">ps = pad from start - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="1246d-140">例: ps/8/#/</span><span class="sxs-lookup"><span data-stu-id="1246d-140">Example: ps/8/#/</span></span>  
  
 <span data-ttu-id="1246d-141">(にパスワードがない場合は、最小限の 8 文字の先頭になるまでの文字 '#' の長さでが 8 文字に合計)</span><span class="sxs-lookup"><span data-stu-id="1246d-141">(if the password is not at least 8 chars in length then pad from the start with the character '#' until there are 8 chars total)</span></span>  
  
 <span data-ttu-id="1246d-142">(' Cat' に '###Cat')</span><span class="sxs-lookup"><span data-stu-id="1246d-142">('Cat' to '#####Cat')</span></span>  
  
 <span data-ttu-id="1246d-143">pe = 末尾の数 (パスワードの最小長) を挿入する 1 文字の後に続くに挿入</span><span class="sxs-lookup"><span data-stu-id="1246d-143">pe = pad from end - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="1246d-144">例: pe/10/$/</span><span class="sxs-lookup"><span data-stu-id="1246d-144">Example: pe/10/$/</span></span>  
  
 <span data-ttu-id="1246d-145">(パスワードがない場合に 10 文字以上で、長さ、そこまでの文字 '$' の末尾が 10 文字の合計)</span><span class="sxs-lookup"><span data-stu-id="1246d-145">(if the password is not at least 10 chars in length then pad to the end with the character '$' until there are 10 chars total)</span></span>  
  
 <span data-ttu-id="1246d-146">('Cat$ $$' には ' cat')</span><span class="sxs-lookup"><span data-stu-id="1246d-146">('Cat' to 'Cat$$$$$$$')</span></span>  
  
 <span data-ttu-id="1246d-147">tr = 切り捨て - 続けて数の文字列の長さの制限</span><span class="sxs-lookup"><span data-stu-id="1246d-147">tr = truncate - limit length of string - followed by count</span></span>  
  
 <span data-ttu-id="1246d-148">例: tr/11/</span><span class="sxs-lookup"><span data-stu-id="1246d-148">Example: tr/11/</span></span>  
  
 <span data-ttu-id="1246d-149">('Cat123456789' to 'Cat12345678');</span><span class="sxs-lookup"><span data-stu-id="1246d-149">('Cat123456789' to 'Cat12345678');</span></span>  
  
 <span data-ttu-id="1246d-150">トークンは、文字列内の順序で処理されます。</span><span class="sxs-lookup"><span data-stu-id="1246d-150">The tokens are processed in their order in the string.</span></span>  
  
 <span data-ttu-id="1246d-151">例:</span><span class="sxs-lookup"><span data-stu-id="1246d-151">Example:</span></span>  
  
 <span data-ttu-id="1246d-152">uc/rc/1/(& a)/sc/2/#$/--/ps/8/&/tr/32/</span><span class="sxs-lookup"><span data-stu-id="1246d-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span></span>