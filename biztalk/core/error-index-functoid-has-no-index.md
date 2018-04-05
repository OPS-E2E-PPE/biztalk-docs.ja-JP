---
title: エラー - インデックス Functoid にインデックスがありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasNoIndex
ms.assetid: a523705e-6134-4d98-8ea6-dbfc7b43dae5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0159d308c9befc90590d281351409ba571921a53
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="error---index-functoid-has-no-index"></a>エラー - インデックス Functoid にインデックスがありません。
**エラー コード**  
  
 btm1014  
  
 **説明**  
  
 インデックス値が指定されていない対象**インデックス**functoid です。  
  
 **ユーザーの操作**  
  
 対象の適切な数のインデックス入力パラメーターを提供**インデックス**functoid は、適切な数は、ループの数によって決定されます、**レコード**を内のノード、 **フィールド**送信元スキーマ内のノードで入れ子になっています。 インデックス入力パラメーターを作成するには、対象の functoid を選択して、省略記号ボタンをクリックして (**.**) に関連付けられたボタン、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、次を使用して、 ![ ] (../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert")ボタンを**構成\<Functoid\> Functoid**最初の 1 つが直接の親にインデックスを表す 1 つまたは複数の定数入力パラメーターを追加するダイアログ ボックスループ**レコード**ノード、および後続のインデックス入力パラメーターがますますリモートの祖先のループを表す**レコード**ノード。