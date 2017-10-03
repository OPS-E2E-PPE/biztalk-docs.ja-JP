---
title: "エラー - インデックス Functoid にインデックスがありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.indexFunctoidHasNoIndex
ms.assetid: a523705e-6134-4d98-8ea6-dbfc7b43dae5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8143442b9d77d6881efe2b64dfb7f5888ab2d466
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---index-functoid-has-no-index"></a>エラー - インデックス Functoid にインデックスがありません。
**エラー コード**  
  
 btm1014  
  
 **説明**  
  
 インデックス値が指定されていない対象**インデックス**functoid です。  
  
 **ユーザーの操作**  
  
 対象の適切な数のインデックス入力パラメーターを提供**インデックス**functoid は、適切な数は、ループの数によって決定されます、**レコード**を内のノード、 **フィールド**送信元スキーマ内のノードで入れ子になっています。 インデックス入力パラメーターを作成するには、対象の functoid を選択して、省略記号ボタンをクリックして (**.**) に関連付けられたボタン、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、次を使用して、![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert")ボタンを**構成\<Functoid > Functoid**  ダイアログ ボックスには、最初の 1 つが直接の親ループのインデックスを表す位置を 1 つまたは複数の定数入力パラメーターを追加する**レコード**ノード、および後続のインデックス入力パラメーターますますリモートの祖先のループを表す**レコード**ノード。