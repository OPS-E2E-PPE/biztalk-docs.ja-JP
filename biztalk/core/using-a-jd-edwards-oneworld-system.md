---
title: "JD Edwards OneWorld システムを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 835432e50bce3f347e6f769fb8182ab35fc4f949
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-jd-edwards-oneworld-system"></a>JD Edwards OneWorld システムの使用
JD Edwards OneWorld システムに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムからアクセスするには、JD Edwards OneWorld アダプターを使用します。 このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。  
  
 JD Edwards OneWorld ラボ作業は 2 つのパートに分かれています。 この最初のラボ (ラボ 1) では、JD Edwards OneWorld システムを使用しますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] などの Microsoft 製品はなくてもかまいません。 JD Edwards OneWorld クライアント ツールを使用して JD Edwards OneWorld データベースに接続し、アドレスに基づいて特定のレコードを見つけます。  
  
 2 番目のラボ (ラボ 2) では、BizTalk プロジェクトおよびオーケストレーションを作成します。 アプリケーションを作成したら、アプリケーションを展開し、JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに接続します。 目標は、アダプターを使用して BizTalk アプリケーションを介してデータにアクセスすることです。  
  
## <a name="prerequisites"></a>前提条件  
 このラボの手順を実行するには、JD Edwards OneWorld クライアント ソフトウェアと最新の更新プログラムをインストールする必要があります。 クライアント ソフトウェア ツールを使用するには、JD Edwards OneWorld データベースと、このデータベースへのネットワーク接続、およびそのシステムでのユーザー アカウントが必要です。 このラボでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はなくてもかまいません。  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a>ラボ 1 - JD Edwards OneWorld システムを使用する  
 このラボでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンポーネントは一切使用せずに JD Edwards OneWorld システムを使用します。 目標は、JD Edwards OneWorld への接続のテストと、2 番目のラボが適切に動作する環境であることの確認です。 JD Edwards OneWorld データベース内のデータ テーブルの作成と操作には、JD Edwards OneWorld SQL Plus ツールを使用します。  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a>ラボ 1 の手順 - JD Edwards OneWorld システムを使用する  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a>ブラウザーを使用して JD Edwards OneWorld にログインするには  
  
-   JD Edwards OneWorld システムにログインするには、JD Edwards OneWorld アイコンをクリックします。 入力してください、**ユーザー ID**、**パスワード**、および**環境**、順にクリック**OK**です。  
  
     ![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a>JD Edwards OneWorld のデータを見つけて表示するには  
  
1.  成功したログオンを配置するには**JD Edwards OneWorld Explorer**です。  
  
     ![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")  
  
2.  展開**Master Directory**、し**Foundation Systems**、し**アドレス帳**、し**毎日の処理**です。  
  
     ![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")  
  
3.  右側のウィンドウをダブルクリック**Address Book Revisions**です。  
  
     ![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")  
  
4.  **Alpha Name**、入力`Ga`を選択、**表示アドレス**チェック ボックスをオンし、をクリックして**検索**ツールバーのです。  
  
     ![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")  
  
     **Address Book Revisions - [Work With Addresses]**ダイアログ ボックスで、2 つのレコードが、検索結果として表示されます。  
  
     ![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")  
  
     オフには、データを検索する代替方法、 **Alpha Name**フィールドに、上のテキスト ボックス内をクリックして、**アドレス番号**列、入力と`500`です。 をクリックして**検索**ツールバーの検索結果を表示します。  
  
     ![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")  
  
     ラボ 2 でがあります、JD Edwards OneWorld アダプターを使用して情報を取得するための指示、**アドレス番号**の`500`します。  
  
5.  **ファイル** メニューのをクリックして**終了**では Edwards OneWorld クライアント セッションを終了します。  
  
## <a name="summary"></a>概要  
 このラボでは、JD Edwards OneWorld クライアント ツールを使用して JD Edwards OneWorld システムにログインしました。 システムに接続した後で、特定のデータを検索して返されたデータ レコードを表示しました。