---
title: "追跡プロファイルを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 676ae7e8-f3eb-45f1-ad2e-807b434c0bf9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f5d6cbb210cb292cd8ae7d0e2f4ff811984377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-tracking-profile"></a>追跡プロファイルを作成する方法
展開されたアセンブリおよび BizTalk Server メッセージング プロパティに BAM アクティビティ定義をリンクするために、追跡プロファイルを作成します。 追跡プロファイル エディターを開くと、インポート アクティビティ リンクまたはインポートのメニュー項目をクリックして、新しい追跡プロファイルを作成できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件を次に示します。  
  
-   アクセス許可のある既存の BizTalk 管理データベース  
  
-   BizTalk 管理データベースを使用するように構成された TPE  
  
-   BAM プライマリ インポート データベースにある既存の BAM アクティビティ定義  
  
### <a name="to-create-a-tracking-profile"></a>追跡プロファイルを作成するには  
  
1.  コンピューターまたは送信元システムとして指定したコンピューターで、開く、**追跡プロファイル エディター**です。 これを行うには、をクリックして**開始**、 をクリックして**実行**、型**BTSTrkEditor.exe**、クリックして**ok**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  TPE の左ペインの途中でクリックして**ここをクリックして、BAM アクティビティ定義をインポートする**リンクします。 開き、 **BAM アクティビティ定義のインポート** ダイアログ ボックス。  
  
3.  **BAM アクティビティ定義名**ボックスの一覧が、追跡を基になるアクティビティを選択します。 アクティビティ名の一部を入力することができます、リストに多くの展開済みアクティビティが含まれている場合、**文字列**テキスト ボックスをクリック、**検索**ボタンをクリックします。 これにより、アクティビティの一覧には、入力した文字列が含まれているアクティビティだけが表示されます。  
  
4.  アクティビティを選択すると、クリックして、 **OK**ボタンをクリックします。 これにより、選択したアクティビティに基づいた新しい追跡プロファイルが開き、TPE の左ペインにこのプロファイルが表示されます。  
  
## <a name="see-also"></a>参照  
 [追跡プロファイルを作成します。](../core/creating-tracking-profiles.md)