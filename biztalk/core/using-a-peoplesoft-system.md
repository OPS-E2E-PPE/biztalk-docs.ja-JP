---
title: PeopleSoft システムの使用 |Microsoft ドキュメント
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
ms.openlocfilehash: c93e025ddb2ccec4b0088c20837a4f307f40aada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287378"
---
# <a name="using-a-peoplesoft-system"></a>PeopleSoft システムの使用
PeopleSoft システムは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムから PeopleSoft アダプターを使用してアクセスできます。 このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。  
  
 PeopleSoft ラボ作業は 2 つのパートに分かれています。 この最初のラボ (ラボ 1) では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] またはその他の Microsoft 製品 (Internet Explorer は例外ですが、任意のブラウザーを使用可能) を使用しなくても、PeopleSoft システムを使用できます。 このラボでは、PeopleSoft システムに接続して単純なデータ レコードを検索し、変更します。  
  
 2 番目のラボ (ラボ 2) では、BizTalk プロジェクトおよびオーケストレーションを作成します。 アプリケーションの作成後、そのアプリケーションを展開および利用し、PeopleSoft アダプターを使用して PeopleSoft システムに接続します。 目標は、アダプターを使用して BizTalk アプリケーションを介してデータにアクセスすることです。  
  
## <a name="prerequisites"></a>前提条件  
 このラボの手順を実行するには、ブラウザー、インターネット接続、および PeopleSoft のユーザー アカウントが必要です。 また、PeopleSoft システムに Web でアクセスするには、参照先を知っている必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または他の Microsoft テクノロジは必要ありません。  
  
## <a name="lab-1---using-a-peoplesoft-system"></a>ラボ 1 - PeopleSoft システムの使用  
 このラボでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンポーネントを使用せずに、PeopleSoft システムを使用します。 目標は、2 番目のラボが適切に動作するように、PeopleSoft への接続をテストすることです。 まず、Web インターフェイスを介して PeopleSoft システムに接続します。システムには、Internet Explorer などのブラウザーを使用してログオンできます。  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a>ラボ 1 の手順 - PeopleSoft システムの使用  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a>ブラウザーを使用して PeopleSoft にログオンするには  
  
-   PeopleSoft ログオン ページを参照して、PeopleSoft システムにログインします。 入力、**ユーザー ID**と**パスワード** をクリックし、**サイン イン**です。  
  
     ![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a>PeopleSoft データを検索および変更するには  
  
1.  ログオンが完了すると、レイアウトを選択して表示するコンテンツを個人用に設定できるページが表示されます。 下へスクロールし、展開**財務/サプライ チェーンの設定**、 をクリックして**共通定義**をクリックして**場所**、順にクリック**場所**もう一度です。 表示、**場所**検索インターフェイスです。  
  
     ![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")  
  
2.  検索を開始するには、次のように設定します**SetID**に **=** 、設定されて**場所コード**に**で始まる**、入力 **、。**、クリックして**検索**です。 A で始まる名前の都市が表示されます、**検索結果**インターフェイスのセクションです。  
  
     ![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")  
  
3.  詳細情報を表示するには、いずれかの場所をクリックします。 たとえば、次の図に、ユーザーがクリックした、 **AUS01**内のリンク、**場所コード**列です。  
  
4.  フィールドのいずれかに新しいデータの一部を入力してください (など、**アドレス 2**フィールド) をクリック**保存**左下隅にあります。 新しく入力したデータはレコードに保存されます。  
  
     ![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")  
  
5.  この変更が確実に行われたことを確認するには、手順 2. のプロセスを繰り返して同じレコードを再検索し、レコードの変更結果を確認します。  
  
6.  ウィンドウの右上隅の部分で、クリックして**サインアウト**PeopleSoft セッションを終了します。  
  
     ![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")  
  
    > [!NOTE]
    >  次のラボでは、PeopleSoft アダプターを使用して、変更した場所レコード (AUS01) の情報を取得する手順を示します。  
  
## <a name="summary"></a>概要  
 このラボでは、ブラウザーを介して PeopleSoft システムにログオンしました。 接続後にデータを検索し、レコードのアドレス フィールドを操作および更新しました。 変更終了後は、ブラウザーで変更されたデータを表示し、変更が適切に実行されたことを確認しました。