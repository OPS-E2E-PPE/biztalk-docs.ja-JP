---
title: 展開およびポリシーとボキャブラリを展開解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- policies, deploying
- deploying, vocabularies
- policies, undeploying
- vocabularies, deploying
ms.assetid: 9a7e3310-54b7-482c-8210-b4b11fde4c49
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff5e213cc0ad820bbaa6129ee5e6cf816c3ba0b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385283"
---
# <a name="how-to-deploy-and-undeploy-policies-and-vocabularies"></a>展開およびポリシーとボキャブラリを展開解除する方法
ルール エンジン展開ウィザードを使用して、展開またはポリシーを展開解除することができます。  
  
 ルール エンジン展開ウィザードを展開しようとするときにのみ公開されたポリシー バージョンがドロップダウン リストで表示されます。 展開を解除しようとするときにのみのバージョンがドロップダウン リストで示すようにポリシーを配置します。  
  
### <a name="to-deploy-or-undeploy-a-policy"></a>展開またはポリシーを展開解除するには  
  
1. をクリックして**開始**、 をポイント**Program Files**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**ビジネス ルール エンジン展開ウィザード**します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2. **ルール エンジン展開ウィザード**ようこそ ページで、**次**します。  
  
3. いずれかを選択**ポリシーの展開**または**ポリシーの展開解除**、 をクリックし、**次**。  
  
4. ドロップダウン リストから、使用可能な SQL Server コンピューターと、データベースを選択し、クリックして**次**します。  
  
   > [!NOTE]
   >  に対して構成されているルール ストア データベースにのみ展開できます。 さまざまな DB にデプロイしようとすると、エラーが表示されます。  
  
5. ドロップダウン リストからポリシーを選択し、**次**します。  
  
   > [!NOTE]
   >  展開しようとするとのみ公開されたポリシー バージョンがドロップダウン リストに表示されます。 展開を解除しようとするときにのみのバージョンがドロップダウン リストで示すようにポリシーを配置します。  
  
6. サーバー、データベース、およびポリシーの情報を確認し、クリックして**次**します。  
  
7. 展開または展開解除の進行状況を確認します。 完了したら、クリックして**次**します。  
  
8. 展開または展開解除、完了ステータスを確認し、クリックして**完了**します。  
  
> [!NOTE]
>  展開またはポリシーのバージョンを右クリックし、をクリックして、ビジネス ルール作成ツールから、ポリシー バージョンを展開解除することができますも**デプロイ**または**Undeploy**します。