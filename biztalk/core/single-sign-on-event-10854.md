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
ms.locfileid: "22277578"
---
# <a name="single-sign-on-event-10854"></a>シングル サインオン: イベント 10854
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10854|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_INVALID_STRING_FORMAT|  
|メッセージ テキスト|この関数の文字列形式が正しくありません。|  
  
## <a name="explanation"></a>説明  
 この関数の文字列形式が正しくありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 パスワード文字列の適切な形式について以下で説明します。  
  
 VT_BSTR 型プロパティ  
  
 区切り文字は / (スラッシュ) です  
  
 dc = 既定の状態 (操作なし - 何も行いません)  
  
 例: dc/  
  
 (変更しません - "Cat" は "Cat" になります)  
  
 uc = 大文字  
  
 例: uc/  
  
 (パスワードを大文字に変更します - "Cat" は "CAT" になります)  
  
 lc = 小文字  
  
 例: lc/  
  
 (パスワードを小文字に変更します - "Cat" は "cat" になります)  
  
 rc = 文字を削除します - 続けて文字数と文字を指定します  
  
 例: rc/2/#@/  
  
 ('#' 文字を削除し、' @' のパスワードから 'C@t#'"Ct"に)  
  
 sc = 文字を置換します - 続けて文字数、置換前の文字、置換語の文字を指定します  
  
 例: sc/3/abc/def/  
  
 (パスワードから文字 "a"、"b"、"c" を削除し、"d"、"e"、"f" にそれぞれ置き換えます)  
  
 ("Cat" は "Cdt" になります)  
  
 ps = 先頭に挿入します - 続けて文字数 (パスワードの最小長) と挿入する 1 文字を指定します  
  
 例: ps/8/#/  
  
 (パスワードの長さが 8 文字以上でない場合、全体が 8 文字になるまで、文字列の先頭に文字 "#" を挿入します)  
  
 ("Cat" は "#####Cat" になります)  
  
 pe = 末尾に挿入します - 続けて文字数 (パスワードの最小長) と挿入する 1 文字を指定します  
  
 例: pe/10/$/  
  
 (パスワードの長さが 10 文字以上でない場合、全体が 10 文字になるまで、文字列の末尾に文字 "$" を挿入します)  
  
 ("Cat"になります $$$ ')  
  
 tr = 切り捨てます - 文字列の長さを制限します - 続けて文字数を指定します  
  
 例: tr/11/  
  
 ("Cat123456789" は "Cat12345678" になります)  
  
 トークンは文字列内での順序で処理されます。  
  
 例:  
  
 uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/