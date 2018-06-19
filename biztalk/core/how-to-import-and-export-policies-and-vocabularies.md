---
title: インポートおよびポリシーとボキャブラリをエクスポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- Rule Engine Deployment Wizard
- policies, importing
- vocabularies, exporting
- vocabularies, importing
ms.assetid: c427f686-5908-4f72-9e72-46a5497274ac
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ba7cd8a9fc5d28d1b718e9a47ad6cf2f448ec7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253850"
---
# <a name="how-to-import-and-export-policies-and-vocabularies"></a>ポリシーとボキャブラリをインポートおよびエクスポートする方法
ルール エンジン展開ウィザードを使用して、インポートまたはポリシーまたはボキャブラリをエクスポートすることができます。  
  
> [!NOTE]
>  最初に、ポリシーまたはボキャブラリによって使用されるすべてのボキャブラリをインポートする必要があります。これを行わないと、エラーが発生します。  
  
### <a name="to-import-or-export-a-policy-or-vocabulary"></a>ポリシーまたはボキャブラリをインポート/エクスポートするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**ビジネス ルール エンジン展開ウィザード**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  [ようこそ] ページで、をクリックして**次**です。  
  
3.  **展開タスク** ページで、いずれかを選択**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**または**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、し、をクリックして**次**です。  
  
4.  **ポリシー ストア** ページで、ドロップダウン リストからを選択、使用可能な SQL Server コンピューターとデータベース、およびクリック**次**です。  
  
5.  **ポリシー/ボキャブラリのエクスポート** ページで、次の操作をクリックして**次**です。  
  
    1.  選択**ポリシー**または**ボキャブラリ**エクスポート/インポートする対象によって異なります。  
  
    2.  **ポリシー/ボキャブラリ**ドロップダウン リストで、目的のポリシー/ボキャブラリを選択します。  
  
    3.  をクリックして**参照**定義ファイルを選択します。  
  
6.  サーバー、データベース、およびポリシーまたはボキャブラリの情報を確認し、クリックして**次**です。  
  
7.  インポートまたはエクスポートが完了したらをクリックして**次**です。  
  
8.  インポートやエクスポートの完了ステータスを確認し、クリックして**完了**です。