---
title: Resolver クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f4ad2846396e3e59cd4729d3410038495b2edcd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399712"
---
# <a name="the-resolver-class"></a>競合回避モジュール クラス
**リゾルバー**クラスは、名前/値ペアを公開する単純な構造体。 リゾルバー Web サービスは、そのメソッドからこのクラスのインスタンスのジェネリック コレクションを返します。  
  
 ESB コア インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**アセンブリをグローバル アセンブリ キャッシュに競合回避モジュールのクラスを使用します。  
  
 ディクショナリ ベースの名前/値の使用のアプローチを解放し、解決方法と現在の競合回避モジュールの種類に依存する関連のないプロパティを含めることを回避することで解決結果のサイズを最小限に抑えるに簡単に後で新しい項目を追加します。  
  
 **リゾルバー**クラスは、2 つのプロパティを公開します。  
  
-   **名前**です。 これは、接続文字列が解決された後に返される情報を含む名前/値ペアの名前です。  
  
-   **値**。 これは、名前/値ペアの名前に対応する値です。