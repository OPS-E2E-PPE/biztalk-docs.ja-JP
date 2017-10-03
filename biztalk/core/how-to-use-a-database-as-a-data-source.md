---
title: "データ ソースとしてデータベースを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Business Rule Composer, data sources
ms.assetid: a68057ed-836f-499f-bb80-f644d81bcfc5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a9201ee729288a819a3d527a6ecb4fefd32797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-a-database-as-a-data-source"></a>データベースをデータ ソースとして使用する方法
データベースをデータ ソースとして指定できます。 データベースからテーブルまたはテーブルの列を続けて選択し、ファクトとして使用するボキャブラリ定義またはルール上にドラッグできます。  
  
> [!NOTE]
>  いずれかを使用してデータベース行/テーブルにバインドすることもできます**DataConnection**または**TypedDataTable**から「データ接続」や「データベースのテーブルの行/」を選択して、**データベース バインドの種類**ドロップダウン ボックスの [プロパティ] ウィンドウで、**データベース**ファクト エクスプ ローラーのタブ。 **DataConnection**既定によってバインディングを使用します。  
  
### <a name="to-specify-a-sql-database-as-a-data-source"></a>SQL データベースをデータ ソースとして指定するには  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、**データベース**タブです。  
  
2.  右クリックし、**サーバー**ノードをクリックして**参照**です。  
  
3.  ドロップダウン リストで、利用可能なデータベース サーバーを選択します。  
  
4.  認証の種類を選択します。 SQL Server 認証を選択した場合は、ログイン名とパスワードを入力します。 ユーザーの認証情報を入力したら、をクリックして**OK**です。  
  
     ![ツリー ブラウザーのデータベースのスクリーン ショット。] (../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")  
データベースの参照  
  
> [!NOTE]
>  SQL Server データベースのビューはサポートされていません。