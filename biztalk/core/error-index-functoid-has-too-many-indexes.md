---
title: エラー - インデックス Functoid にインデックスが多すぎる |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasTooManyIndices
ms.assetid: 5dd2d5b4-3f7a-45be-b6f4-708b0a76805a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a22b49a921b957c0fb36f9e6b6925c991cc3cf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968944"
---
# <a name="error---index-functoid-has-too-many-indexes"></a>エラー - インデックス Functoid にインデックスが多すぎます
**エラー コード**  
  
 btm1016  
  
 **説明**  
  
 指定された**インデックス**functoid が多すぎますインデックス入力パラメーターを指定します。 インデックス入力パラメーターの数が、祖先のループの数を超えない**レコード**を内のノード、**フィールド**最初の入力パラメーターが入れ子になったとして指定されたノード。  
  
 **ユーザーの操作**  
  
 選択し**インデックス**functoid は、省略記号ボタン (**.**) に関連付けられたボタン、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウにし、**構成\<Functoid\>Functoid**ダイアログ ボックスで、削除を選択しをクリックすると、余分なインデックス入力パラメーター、 ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")それぞれのボタンをクリックします。