---
title: 文字列 Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d73be02-9c93-481f-81e4-39b60bcfa2df
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06bcb1d42a5e72a57765d17c18a48b6f4808d412
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278530"
---
# <a name="string-functoids"></a>文字列 Functoid

## <a name="overview"></a>概要
**文字列**functoid はすべて大文字または小文字ではすべて、文字列の連結、文字列の長さ、トリミング、空白文字への変換などの標準的な方法で文字列を操作するために使用します。  
  
 Functoid**大文字**、**小文字**、**サイズ**、**文字列右スペース削除**、および**文字列左スペース削除**1 つしか入力パラメーターを受け入れます。 Functoid**文字列位置検出**、**左文字列抽出**、および**右文字列抽出**2 つの入力パラメーターを受け入れます。 **文字列抽出**functoid は 3 つの入力を受け取りませんが、**文字列連結**functoid は 1 ~ 100 の範囲の入力パラメーターを受け取ります。  
  
 2 つ**文字列**functoid は、文字列の文字の数値の位置を参照してください:**文字列抽出**と**文字列位置検出**です。 これらの Functoid は、文字位置を 1 (0 ではない) からカウントします。  
  
 2 つ文字列を切り捨てる functoid、**文字列左スペース削除**と**文字列右スペース削除**、すべての空白文字 (スペース、タブ、およびなど) から削除左または右 (場合もあります)、指定した文字列の。  

## <a name="available-functoids"></a>使用可能な functoid 
 **文字列**functoid には。 

* 小文字
* サイズ
* 文字列連結します。
* 文字列抽出
* 文字列位置検出
* 左文字列抽出
* 文字列左スペース削除
* 右文字列抽出
* 文字列右スペース削除
* 大文字

これらの functoid の詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="see-also"></a>参照  
-  [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **文字列 Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]