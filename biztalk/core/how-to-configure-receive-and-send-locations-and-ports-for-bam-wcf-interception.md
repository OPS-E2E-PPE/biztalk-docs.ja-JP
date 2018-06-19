---
title: 構成する方法の場所と送受信ポートを BAM WCF インターセプション用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501194dc-427a-4910-88c9-19cf47daeaad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa77f39e8320c0d6598caaf5ea547592078774ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248442"
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a>BAM WCF 傍受のために受信および送信場所とポートを構成する方法
この手順では、重要な概念をわかりやすく示すために、コンテンツ ベースのルーティング (CBR) のシナリオで受信場所と送信場所を構成します。 ここで示す概念は、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] サービスとして公開されるオーケストレーションに適用できます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順では、次のことを前提としています。  
  
-   ように、machince.config ファイルを変更[BAM インターセプタ動作を Machine.config ファイルに追加する方法](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)です。  
  
-   WCF アダプターを BizTalk server でスライド ショーとして作成[BizTalk Server の WCF アダプターを作成する方法](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)です。  
  
### <a name="to-configure-the-receive-and-send-locations"></a>受信場所と送信場所を構成するには  
  
1.  BizTalk 管理コンソールを開きます。 これを行うには、をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、クリックして**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーを展開し、BizTalk アプリケーションの [受信場所] ノードを探します。 をクリックして[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 をクリックして**アプリケーション**で選択したアプリケーションをクリックして、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]クリックしてサービスの種類 ダイアログ ボックス、**受信場所**です。 作成した受信場所に対応する、新しい受信場所が作成されます。 新しい受信場所は、無効な状態になります。  
  
3.  開くには、受信場所をダブルクリックして、**受信場所のプロパティ** ダイアログ ボックス、および WCF カスタム トランスポートの種類としてを選択します。  
  
4.  クリックして、**構成**を開く ボタン、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。  
  
5.  クリックして、**バインディング**タブし、使用するバインディングを選択します。  
  
6.  クリックして、**動作** タブで、右クリックし、 **endpointbehavior**ノードをクリックして**拡張機能の追加**です。  
  
7.  BAMEndPointExtension (machine.config ファイルに追加した拡張機能) を選択し、クリックして**Ok**です。  
  
     ![動作拡張機能の選択画面](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")  
  
8.  作成した拡張機能を選択、次の値を入力し、クリックして**OK**:  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |PollingIntervalSec|10|  
    |ConnectionString|ConnectionString: 統合セキュリティを = SSPI;Persist Security Info = False; Initial Catalog = BAMPrimaryImport; データ ソース =|  
  
9. **受信場所のプロパティ**ダイアログ ボックスで、 **PassThruReceive**から、**受信パイプライン**クリックしてドロップダウン リスト、 **OK**.  
  
10. 受信場所を有効にし、管理コンソールを更新します。 開始状態は、設定が正常に行われたことを示します。  
  
## <a name="see-also"></a>参照  
 [BAM データを受信する WCF アダプタの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)