---
title: JD Edwards OneWorld システムの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fb7bdef551f0ceb66e8eea5ea1fe073bd0bca72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399925"
---
# <a name="using-a-jd-edwards-oneworld-system"></a>JD Edwards OneWorld システムの使用
JD Edwards OneWorld システムはからアクセスできる、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] JD Edwards OneWorld アダプターを使用してシステム。 このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。  
  
 JD Edwards OneWorld ラボ作業は、2 つの部分に分かれています。 この最初のラボ (ラボ 1) では、JD Edwards OneWorld システムをしなくても使用できます。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]などの Microsoft 製品です。 JD Edwards OneWorld データベースに接続し、アドレスに基づいて特定のレコードを検索するには、JD Edwards OneWorld クライアント ツールは使用します。  
  
 2 番目のラボ (ラボ 2) では、BizTalk プロジェクトおよびオーケストレーションを作成します。 アプリケーションを作成した後は、デプロイし、JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムへの接続に使用されます。 目標は、アダプターを使用して BizTalk アプリケーションを介してデータにアクセスします。  
  
## <a name="prerequisites"></a>前提条件  
 このラボの手順を実行するには、JD Edwards OneWorld クライアント ソフトウェアと最新の更新プログラムをインストールする必要があります。 クライアントのソフトウェア ツールを使用するには、JD Edwards OneWorld データベース、そのデータベースとそのシステム上のユーザー アカウントへのネットワーク接続を必要があります。 必要としない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この演習を完了します。  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a>ラボ 1 - JD Edwards OneWorld システムの使用  
 この演習では、すべてのコンポーネントを使用せず、JD Edwards OneWorld システムを使用します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 目標は、JD Edwards OneWorld への接続をテストし、2 番目のラボが正しく機能することを確認します。 JD Edwards OneWorld SQL Plus ツールを使用して、作成し、JD Edwards OneWorld データベース内のデータ テーブルを操作します。  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a>ラボ 1 - JD Edwards OneWorld システムの使用の手順  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a>ブラウザーを使用して JD Edwards OneWorld にログオンするには  
  
-   JD Edwards OneWorld アイコンをクリックして、JD Edwards OneWorld システムにログオンします。 入力、**ユーザー ID**、**パスワード**と**環境**、順にクリックします**OK**します。  
  
     ![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a>検索して JD Edwards OneWorld のデータを表示するには  
  
1.  成功したログオンを配置するには**JD Edwards OneWorld Explorer**します。  
  
     ![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")  
  
2.  展開**Master Directory**、し**Foundation Systems**、し**アドレス帳**、し**毎日処理**。  
  
     ![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")  
  
3.  右側のウィンドウでダブルクリック**Address Book Revisions**します。  
  
     ![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")  
  
4.  **Alpha Name**、入力`Ga`を選択します、**表示アドレス**チェック ボックスをオンにして**検索**ツールバーの。  
  
     ![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")  
  
     **Address Book Revisions - [Work With Addresses]** ダイアログ ボックスで、検索結果として 2 つのレコードが表示されます。  
  
     ![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")  
  
     オフにする代替のデータを検索する方法は、 **Alpha Name**フィールドに、上記のテキスト ボックス内をクリックして、**アドレス番号**列、入力と`500`します。 クリックして**検索**ツールバーの検索結果を表示します。  
  
     ![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")  
  
     ラボ 2 でがありますを JD Edwards OneWorld アダプターを使用して情報を取得する手順については、**アドレス番号**の`500`します。  
  
5.  **ファイル** メニューのをクリックして**終了**JE Edwards OneWorld クライアント セッションを終了します。  
  
## <a name="summary"></a>まとめ  
 この演習では、JD Edwards OneWorld クライアント ツールを使用して JD Edwards OneWorld システムにログオンします。 、接続された後は、特定のデータを検索し、返されるデータ レコードを表示します。