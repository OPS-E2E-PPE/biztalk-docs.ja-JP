---
title: 追跡プロファイルを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 676ae7e8-f3eb-45f1-ad2e-807b434c0bf9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb5951042bc3f3bbc3c2379cc83ab07de0d35c0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385552"
---
# <a name="how-to-create-a-tracking-profile"></a>追跡プロファイルを作成する方法
BAM アクティビティ定義を展開したアセンブリおよび BizTalk Server メッセージング プロパティにリンクする追跡プロファイルを作成します。 追跡プロファイル エディターを開くと、インポート アクティビティ リンクまたはインポートのメニュー項目をクリックして、新しい追跡プロファイルを作成できます。  
  
## <a name="prerequisites"></a>前提条件  
 次に、このトピックの手順を実行するための前提条件を示します。  
  
-   アクセス許可がある既存の BizTalk 管理データベース。  
  
-   TPE は、BizTalk 管理データベースを使用するよう構成します。  
  
-   BAM プライマリ インポート データベースの既存の BAM アクティビティ定義。  
  
### <a name="to-create-a-tracking-profile"></a>追跡プロファイルを作成するには  
  
1.  コンピューターまたはソース システムとして指定したコンピューターで、開く、**追跡プロファイル エディター**します。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、型**BTSTrkEditor.exe**、順にクリックします**OK**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  TPE の左ペインの途中で次のようにクリックします。**ここをクリックすると、BAM アクティビティ定義をインポートする**リンク。 開き、 **BAM アクティビティ定義のインポート** ダイアログ ボックス。  
  
3.  **BAM アクティビティ定義名**リスト ボックスは、追跡を基になるアクティビティを選択します。 一覧に多くの展開済みアクティビティが含まれている場合は、アクティビティ名の一部を入力、**文字列**テキスト ボックスをクリックして、**検索**ボタンをクリックします。 これは、名前が入力した文字列を含むものに表示されるアクティビティの一覧を制限します。  
  
4.  アクティビティを選択すると、クリックして、 **OK**ボタン。 選択したアクティビティに基づいた新しい追跡プロファイルを開き、TPE の左ペインでプロファイルが表示されます。  
  
## <a name="see-also"></a>参照  
 [追跡プロファイルの作成](../core/creating-tracking-profiles.md)