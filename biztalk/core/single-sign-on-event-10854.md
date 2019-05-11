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
# <a name="single-sign-on-event-10854"></a>シングル サインオン:イベント 10854
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10854                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |               ENTSSO_E_INVALID_STRING_FORMAT               |
|  メッセージ テキスト   |     この関数の文字列の形式が正しくないです。      |
  
## <a name="explanation"></a>説明  
 この関数の文字列の形式が正しくないです。  
  
## <a name="user-action"></a>ユーザーの操作  
 次のとおり、パスワードの文字列の適切な形式します。  
  
 VT_BSTR 型プロパティ  
  
 区切り記号は/(スラッシュ)  
  
 dc = 既定のケース (操作なし - 何もしない)  
  
 例: dc/  
  
 (変更なし -"Cat"は"Cat"に)  
  
 uc = 大文字  
  
 例: uc/  
  
 (パスワードを大文字に変換 -"Cat"は"CAT"に変更します)  
  
 lc = 小文字  
  
 例: lc/  
  
 (大文字と小文字の-"Cat"は"cat"にするパスワードを変更する)  
  
 rc = 文字を削除します-続けて文字数  
  
 例: rc/2/#@/  
  
 ('#' 文字を削除し、' @' からパスワード - 'C@t#' ct)  
  
 sc = 文字に置換する文字数を続けての代替文字が続く代替  
  
 例: sc/3/abc/def/  
  
 (文字 'a'、'b' を削除しでのパスワードと置換から ' c' が '、'e' と 'f' それぞれ)  
  
 ("Cat"Cdt を)  
  
 ps = 先頭に挿入の数 (パスワードの最小長) を挿入する 1 文字の後に  
  
 例: ps/8/#/  
  
 (にパスワードがない場合は、最小限の 8 文字の先頭になるまでの文字 '#' の長さでが 8 文字に合計)  
  
 (' Cat' に '###Cat')  
  
 pe = 末尾の数 (パスワードの最小長) を挿入する 1 文字の後に続くに挿入  
  
 例: pe/10/$/  
  
 (パスワードがない場合に 10 文字以上で、長さ、そこまでの文字 '$' の末尾が 10 文字の合計)  
  
 ('Cat$ $$' には ' cat')  
  
 tr = 切り捨て - 続けて数の文字列の長さの制限  
  
 例: tr/11/  
  
 ('Cat123456789' to 'Cat12345678');  
  
 トークンは、文字列内の順序で処理されます。  
  
 例:  
  
 uc/rc/1/(& a)/sc/2/#$/--/ps/8/&/tr/32/