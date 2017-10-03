---
title: "展開およびポリシーとボキャブラリを展開解除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, policies
- policies, deploying
- deploying, vocabularies
- policies, undeploying
- vocabularies, deploying
ms.assetid: 9a7e3310-54b7-482c-8210-b4b11fde4c49
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef36df71459935b588f54c1dadc30ab02a7e722e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-and-undeploy-policies-and-vocabularies"></a>ポリシーとボキャブラリを展開および展開解除する方法
ポリシーの展開と展開解除には、ビジネス ルール エンジン展開ウィザードを使用できます。  
  
 ビジネス ルール エンジン展開ウィザードで展開作業を行う際、公開されたポリシー バージョンだけがドロップダウン リストに表示されます。 展開を解除しようとしたときにのみのバージョンがドロップダウン リストで示すようにポリシーを配置します。  
  
### <a name="to-deploy-or-undeploy-a-policy"></a>ポリシーを展開または展開解除するには  
  
1.  をクリックして**開始**、 をポイント**Program Files**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**ビジネス ルール エンジン展開ウィザード**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  **ルール エンジン展開ウィザード**ようこそ ページで、**次**です。  
  
3.  いずれかを選択**ポリシーの展開**または**ポリシーの展開解除**、順にクリック**次**です。  
  
4.  ドロップダウン リストから、使用可能な SQL Server コンピューターと、データベースを選択し、クリックして**次**です。  
  
    > [!NOTE]
    >  展開先には、ルール ストア データベースのみ選択できます。 それ以外のデータベースに対して展開しようとするとエラーが発生します。  
  
5.  ドロップダウン リストからポリシーを選択し、をクリックして**次**です。  
  
    > [!NOTE]
    >  展開するときは、公開されたポリシー バージョンだけがドロップダウン リストに表示されます。 展開を解除しようとしたときにのみのバージョンがドロップダウン リストで示すようにポリシーを配置します。  
  
6.  サーバー、データベース、およびポリシー情報を確認し、クリックして**次**です。  
  
7.  展開または展開解除の進捗状況が表示されます。 完了すると、**次**です。  
  
8.  展開または展開解除、完了ステータスを確認し、クリックして**完了**です。  
  
> [!NOTE]
>  展開またはポリシーのバージョンを右クリックし、をクリックして、ビジネス ルール作成ツールから、ポリシー バージョンを展開解除することができますも**展開**または**Undeploy**です。