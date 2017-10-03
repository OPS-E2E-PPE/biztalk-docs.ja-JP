---
title: "インポートまたはエクスポートする BizTalk の設定を使用して設定のダッシュ ボード |Microsoft ドキュメント"
description: "BizTalk Server 管理コンソールを使用して、インポートまたは BizTalk Server 環境の間の設定をエクスポートするには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc2f0b44-d79b-4f95-811a-0843e3d6d1c8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e33b8659701ab991f7b7467c8ab3edd8b79def4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-settings-dashboard-to-import-or-export-biztalk-settings"></a>設定ダッシュ ボードを使用して、インポートまたは BizTalk の設定をエクスポートするには 

## <a name="overview"></a>概要
BizTalk 設定ダッシュボードを使用して、ある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートして別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることで、問題解決までの全体的な時間を短縮できます。 これは、管理者がステージング環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整し、適正な結果が得られた時点で設定を実稼働環境にインポートする場合、特に役立ちます。 このトピックでは、設定ダッシュボードを使用して、BizTalk グループ、ホスト、およびホスト インスタンスの設定をインポートする手順を説明します。  

> [!TIP]
> BTSTask コマンド ライン ユーティリティは、インポートまたはグループ、ホスト、およびホスト インスタンスの設定をエクスポートするも使用できます。 参照してください[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。

  
## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。  
  
## <a name="import-the-biztalk-group-host-and-host-instance-settings"></a>BizTalk グループ、ホスト、およびホスト インスタンスの設定をインポートします。  

> [!IMPORTANT]
>  BizTalk Server の設定を特定の環境からインポートするには、それらの設定を XML ファイルとして保存およびエクスポートしておく必要があります。 **BizTalk の設定をエクスポート**(」を参照) または[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)ことができます。
  
 XML ファイルをインポートすることで、対象コンピューターで必要な BizTalk Server 設定をレプリケートできます。 設定ダッシュボードを使用すると、グループ、ホスト、およびホスト インスタンスの設定をインポートし、そのプロパティを相互にマップできます。 次に設定をインポートする際に必要な前提条件を示します。  
  
-   BizTalk Server トポロジがインポート元の環境からインポート先の環境まで一貫している。  
  
-   インポート元の環境からインポート先の環境にまたがるホスト定義をマップできる。 インポート元の環境にあるすべてのホストを、インポート先の環境にあるホストにマップできる。  
  
-   インポート先環境には、インポート元環境と (同じかまたは) 似たハードウェアがあります。 一部の設定は基礎となるハードウェアに依存しているため、これは重要です。  

### <a name="import-steps"></a>インポート手順
  
1.  **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。  
  
2.  **BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、をクリックして**インポート**です。 **設定のインポート ウィザード** ダイアログ ボックスが表示されます。  
  
    > [!NOTE]
    >  **宛先グループ**の設定をインポートする対象コンピューターのグループ情報が表示されます。  
  
     ![設定をインポートするファイルの場所を指定](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")  
  
3.  クリックして、**ファイルの場所を指定** ページで、クリックして![設定ファイルの参照](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse")です。 ファイル エクスプローラーが表示されます。  
  
4.  ソース環境設定を含む XML ファイルを選択し、クリックして**開く**です。 **ファイルの場所**XML ファイルのパスを表示し、**ソース グループ**ソース マシンのグループの情報が格納されます。 **[次へ]**をクリックします。  
  
5.  **ホスト マッピング** ページで、次の操作します。  
  
    1.  **送信先ホスト**一覧で、送信元ホストを指定し、をクリックする移行先ホストを選択**追加**です。  
  
         ![ホスト マッピング](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")  
  
    2.  **ソース エンティティの選択**ダイアログ ボックスでは、ソース ホストを選択し、をクリックして**OK**です。  
  
        > [!NOTE]
        >  1 つのソース ホストに複数の送信先ホストにマップする手順を繰り返します**5a**と**5b**です。  
  
    3.  **ホスト マッピング**] ページで [**次**です。  
  
6.  **ホスト インスタンス マッピング** ページで、次の操作します。  
  
    1.  インポート元ホスト インスタンスを指定し、をクリックする移行先ホスト インスタンスを選択、インポート先ホスト インスタンスの一覧から**追加**です。  
  
        > [!NOTE]
        >  ホスト インスタンスは、ホスト マッピングで指定された対応するホストにのみマップできます。 マッピングを指定する場合など、 **SourceHost1**にマップされて**DestinationHost1**のインスタンス、 **DestinationHost1**インスタンスにしかマップできません**SourceHost1**です。  
        >   
        >  上記の制約はインポート ウィザードによって管理され、この制約に従う必要があります。従わない場合、BizTalk タスクによってエラーがスローされます。  
        >   
        >  規則を使用する必要があります**HostName:MachineName**マップ ファイルのホスト インスタンスを指定します。 たとえば、 **Host1:Server1**マップ ファイルを表しているインスタンスの**Host1**が実行されているか**Server1**です。  
  
         ![ホスト インスタンス マッピング](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")  
  
    2.  **ソース エンティティの選択**ダイアログ ボックスで、インポート元ホスト インスタンスを選択し、をクリックして**OK**です。  
  
        > [!NOTE]
        >  複数のインポート先ホスト インスタンスを 1 つのソース ホストのインスタンスをマップする手順を繰り返します**6a**に**6b**です。  
  
    3.  **ホスト インスタンス マッピング** タブで、をクリックして**次**です。  
  
7.  **インポートの概要**ダイアログ ボックスでは、としての送信先と送信元の環境を作成したすべてのインポート設定がある場合は、必要に応じて、ことを確認し、をクリックして**インポート**です。 **進行**ページ、設定のインポートの進行状況を示しています。  
  
    > [!WARNING]
    >  BizTalk Server 設定のインポートを元に戻すことはできません。 クリックした場合**インポート**、設定のインポート元環境から送信先の環境にプロセスが開始されると**キャンセル**は無効になります。 クリックする前にインポートを続行するかを確認してください。**インポート**です。  
  
8.  **インポート結果** タブで、グループ、ホスト、およびホスト インスタンスの設定のインポートの状態を確認し、をクリックして**完了**インポート操作を完了します。 インポート元の環境からインポートしたすべての設定が、インポート先の環境に適用されます。  
  
     ![結果のインポート](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")  

## <a name="export-the-biztalk-group-host-and-host-instance-settings"></a>BizTalk グループ、ホスト、およびホスト インスタンスの設定をエクスポートします。  

1.  **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。  
  
2.  **BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、をクリックして**エクスポート**です。 **[名前を付けて保存]** ダイアログ ボックスが表示されます。  
  
3.  BizTalk の現在の設定を保存する場所に移動します。 ファイル名を入力、XML 形式で、種類を選択してをクリックして**保存**です。  

> [!IMPORTANT]
>  いないいないはお勧め、エクスポートされた XML ファイルを手動で更新します。 更新された XML ファイルを実稼働環境にインポートするときにデータ型の不一致または手動で編集によって導入されたその他のエラーのため、インポート処理が失敗します。  

## <a name="see-also"></a>参照  
 [BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)