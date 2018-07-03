---
title: インポートまたはエクスポートする BizTalk の設定を使用して設定のダッシュ ボード |Microsoft Docs
description: BizTalk Server 管理コンソールを使用して、インポートまたは BizTalk Server 環境の間の設定をエクスポートするには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc2f0b44-d79b-4f95-811a-0843e3d6d1c8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3713ee7906d735b6328b50d3b97a214422893d21
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970219"
---
# <a name="use-settings-dashboard-to-import-or-export-biztalk-settings"></a>設定ダッシュ ボードを使用して、インポートまたは BizTalk の設定をエクスポートするには 

## <a name="overview"></a>概要
BizTalk 設定ダッシュボードを使用して、ある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートして別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることで、問題解決までの全体的な時間を短縮できます。 これは、管理者がステージング環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整し、適正な結果が得られた時点で設定を実稼働環境にインポートする場合、特に役立ちます。 このトピックでは、設定ダッシュボードを使用して、BizTalk グループ、ホスト、およびホスト インスタンスの設定をインポートする手順を説明します。  

> [!TIP]
> BTSTask コマンド ライン ユーティリティをインポートまたはグループ、ホスト、およびホスト インスタンスの設定をエクスポートすることもできます。 参照してください[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)します。

  
## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。  
  
## <a name="import-the-biztalk-group-host-and-host-instance-settings"></a>BizTalk グループ、ホスト、およびホスト インスタンスの設定をインポートします。  

> [!IMPORTANT]
>  BizTalk Server の設定を特定の環境からインポートするには、それらの設定を XML ファイルとして保存およびエクスポートしておく必要があります。 **BizTalk の設定をエクスポート**(」を参照) または[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)ことができます。
  
 XML ファイルをインポートすることで、対象コンピューターで必要な BizTalk Server 設定をレプリケートできます。 設定ダッシュボードを使用すると、グループ、ホスト、およびホスト インスタンスの設定をインポートし、そのプロパティを相互にマップできます。 次に設定をインポートする際に必要な前提条件を示します。  
  
-   BizTalk Server トポロジがインポート元の環境からインポート先の環境まで一貫している。  
  
-   インポート元の環境からインポート先の環境にまたがるホスト定義をマップできる。 インポート元の環境にあるすべてのホストを、インポート先の環境にあるホストにマップできる。  
  
-   インポート先環境には、インポート元環境と (同じかまたは) 似たハードウェアがあります。 一部の設定は基礎となるハードウェアに依存しているため、これは重要です。  

### <a name="import-steps"></a>インポートの手順
  
1. **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。  
  
2. **BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、をクリックして**インポート**します。 **設定のインポート ウィザード** ダイアログ ボックスが表示されます。  
  
   > [!NOTE]
   >  **宛先グループ**の設定をインポートするターゲット コンピューターのグループ情報を表示します。  
  
    ![設定をインポートするファイルの場所を指定](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")  
  
3. をクリックして、**ファイルの場所を指定**] ページの [クリックして![設定ファイルの参照](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse")します。 ファイル エクスプローラーが表示されます。  
  
4. ソース環境の設定を含む XML ファイルを選択し、クリックして**オープン**します。 **ファイルの場所**XML ファイルのパスが表示されます、**ソース グループ**ソース マシンのグループの情報が表示されます。 **[次へ]** をクリックします。  
  
5. **ホスト マッピング**ページで、次の操作を行います。  
  
   1.  **宛先ホスト**一覧で、ソース ホストを指定し、クリックする移行先ホストを選択します。**追加**します。  
  
        ![ホスト マッピング](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")  
  
   2.  **ソース エンティティの選択** ダイアログ ボックスでは、ソース ホストを選択し、クリックして**OK**します。  
  
       > [!NOTE]
       >  1 つのソースのホストに複数の送信先ホストにマップする手順を繰り返します**5a**と**5b**します。  
  
   3.  **ホスト マッピング**] ページで [**次**します。  
  
6. **ホスト インスタンス マッピング**ページで、次の操作を行います。  
  
   1.  インポート先ホスト インスタンスの一覧から、ソース ホスト インスタンスを指定し、クリックする宛先のホスト インスタンスを選択します。**追加**します。  
  
       > [!NOTE]
       >  ホスト インスタンスは、ホスト マッピングで指定された対応するホストにのみマップできます。 たとえば、次のマッピングを指定する場所**SourceHost1**にマップされます**DestinationHost1**のインスタンスでは、 **DestinationHost1**インスタンスにしかマップできません**SourceHost1**します。  
       >   
       >  上記の制約はインポート ウィザードによって管理され、この制約に従う必要があります。従わない場合、BizTalk タスクによってエラーがスローされます。  
       >   
       >  規則を使用する必要がある**HostName:MachineName**マップ ファイルのホスト インスタンスを指定します。 たとえば、 **Host1:Server1**マップ ファイルを表しているインスタンスの**Host1**が実行中か**Server1**します。  
  
        ![ホスト インスタンス マッピング](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")  
  
   2.  **ソース エンティティの選択** ダイアログ ボックスで、ソース ホスト インスタンスを選択し、順にクリックします**OK**します。  
  
       > [!NOTE]
       >  複数の宛先ホスト インスタンスを 1 つのソース ホスト インスタンスをマップする手順を繰り返します**6a**に**6b**します。  
  
   3.  **ホスト インスタンス マッピング**] タブで [**次**します。  
  
7. **インポートの概要**ダイアログ ボックスで、確認としての送信先と送信元の環境を作成したすべてのインポート設定がある場合は、必要に応じてをクリックして**インポート**します。 **進行状況**ページには、設定のインポートの進行状況が表示されます。  
  
   > [!WARNING]
   >  BizTalk Server 設定のインポートを元に戻すことはできません。 クリックすると**インポート**、送信先の環境にソース環境から設定をインポートするためのプロセスが開始されると**キャンセル**は無効です。 クリックする前にインポートを続行することを確認**インポート**します。  
  
8. **インポート結果** タブで、グループ、ホスト、およびホスト インスタンスの設定のインポートの状態を確認し、をクリックし、**完了**インポート操作を完了します。 インポート元の環境からインポートしたすべての設定が、インポート先の環境に適用されます。  
  
    ![結果のインポート](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")  

## <a name="export-the-biztalk-group-host-and-host-instance-settings"></a>BizTalk グループ、ホスト、およびホスト インスタンスの設定をエクスポートします。  

1. **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。  
  
2. **BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、をクリックして**エクスポート**します。 **[名前を付けて保存]** ダイアログ ボックスが表示されます。  
  
3. BizTalk の現在の設定を保存する場所に移動します。 ファイル名を入力、XML の形式として、種類の選択および順にクリックします**保存**します。  

> [!IMPORTANT]
>  ないいないはお勧め、エクスポートされた XML ファイルを手動で更新します。 運用環境に更新された XML ファイルをインポートすると、インポート プロセスが失敗するデータ型の不一致または手動で編集で導入されたその他のエラーのためです。  

## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)