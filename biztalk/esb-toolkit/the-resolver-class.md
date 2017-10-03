---
title: "競合回避モジュール クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1359bcbb9c6c918fc0ee6d5e67bacb8e3559c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-class"></a>競合回避モジュール クラス
**リゾルバー**クラスは、名前/値ペアを公開する単純な構造体。 競合回避モジュールの Web サービスは、そのメソッドからこのクラスのインスタンスのジェネリック コレクションを返します。  
  
 ESB コア インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**アセンブリをグローバル アセンブリ キャッシュに競合回避モジュールのクラスを使用します。  
  
 ディクショナリ ベースの名前/値の使用により、解放後で新しい項目の追加に簡単になり、解決方法および現在の競合回避モジュールの種類に依存する関連のないプロパティを含めることを回避することで解決の結果のサイズを最小化に近づいています。  
  
 **リゾルバー**クラスは 2 つのプロパティを公開します。  
  
-   **名前**です。 これは、接続文字列が解決された後に返される情報が含まれる名前/値ペアの名前です。  
  
-   **値**。 これは、名前/値ペアの名前に対応する値です。