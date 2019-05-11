---
title: PeopleSoft システムの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c228ac23-184f-4c08-922b-ba84f5f2c52f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b7f98086c5e2be4e236a5691e4ff5633ac5f45b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399943"
---
# <a name="using-a-peoplesoft-system"></a>PeopleSoft システムの使用
PeopleSoft システムは、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムから PeopleSoft アダプターを使用してアクセスできます。 このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。  
  
 PeopleSoft ラボ作業は、2 つの部分に分かれています。 この最初のラボ (ラボ 1) では、PeopleSoft システムをしなくても使用できます。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]などの Microsoft 製品 (ただし、おそらくが Internet Explorer では、任意のブラウザーを使用できます)。 このラボでは、単純なデータ レコードの変更を見つけて、PeopleSoft システムに接続します。  
  
 2 番目のラボ (ラボ 2) では、BizTalk プロジェクトおよびオーケストレーションを作成します。 アプリケーションを作成した後は、デプロイし、PeopleSoft アダプターを使用して PeopleSoft システムへの接続に使用されます。 目標は、アダプターを使用して BizTalk アプリケーションを介してデータにアクセスします。  
  
## <a name="prerequisites"></a>前提条件  
 このラボの手順を実行するには、ブラウザーと PeopleSoft システムでユーザー アカウントと共に、インターネットに接続が必要です。 PeopleSoft システムへの Web アクセスを得るために参照する場所を知る必要があります。 必要としない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または他の Microsoft テクノロジです。  
  
## <a name="lab-1---using-a-peoplesoft-system"></a>ラボ 1 - PeopleSoft システムの使用  
 このラボでのすべてのコンポーネントを使用せず、PeopleSoft システムを使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 目標は、2 番目のラボが正しく機能することを確認する PeopleSoft への接続をテストします。 最初に Internet Explorer などのブラウザーを使用してログオンすることができる Web インターフェイスを介して PeopleSoft システムに接続します。  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a>ラボ 1 - PeopleSoft システムの使用の手順  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a>ブラウザーを使用して PeopleSoft にログオンするには  
  
-   PeopleSoft ログオン ページを参照して、PeopleSoft システムにログオンします。 入力、**ユーザー ID**と**パスワード**順にクリックします**サインイン**します。  
  
     ![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a>PeopleSoft データを検索および変更  
  
1.  成功したログオンは、レイアウトを選択して表示するコンテンツを個人用に設定するページに配置します。 下へスクロールし、展開**財務/サプライ チェーンの設定**、 をクリックして**共通定義**、 をクリックして**場所**、 をクリックし、**場所**もう一度です。 表示、**場所**検索インターフェイス。  
  
     ![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")  
  
2.  検索を開始するには、次のように設定します**SetID**に **=** に設定して、**場所コード**に**で始まる**、入力 **、。**、 をクリックし、**検索**します。 A で始まる名前の都市が表示されます、**検索結果**インターフェイスのセクション。  
  
     ![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")  
  
3.  詳細情報を取得する場所のいずれかをクリックします。 たとえば、次の図に、ユーザー クリックして、 **AUS01**のリンクを**場所コード**列。  
  
4.  フィールドのいずれかに新しいデータを入力します (など、**アドレス 2**フィールド) をクリック**保存**左上隅にあります。 これにより、新しく入力したデータがレコードに保存します。  
  
     ![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")  
  
5.  この変更の成功を確認し、手順 2 からプロセスを繰り返しますし、この同じレコードを見つけ、レコードに加え、変更を確認します。  
  
6.  ウィンドウの右上部分でクリックして**サインアウト**PeopleSoft セッションを終了します。  
  
     ![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")  
  
    > [!NOTE]
    >  次の実習では、PeopleSoft アダプターを使用して、変更した場所レコード (AUS01) の情報を取得するための手順。  
  
## <a name="summary"></a>まとめ  
 このラボでログオンして、ブラウザーを介して PeopleSoft システムにします。 、接続された後、データの検索し操作し、レコードのアドレス フィールドを更新します。 変更をコミットした後でしたデータを表示する変更されたことを確認するには、ブラウザーで適切に実行された変更。