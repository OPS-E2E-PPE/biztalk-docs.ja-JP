---
title: 構成する方法が表示され、BAM WCF 傍受のための場所とポートの送信 |Microsoft Docs
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
ms.openlocfilehash: f9e74d8ef0f6d58b005cf5af873718c927c55dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386199"
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a>BAM WCF 傍受のために受信および送信場所とポートを構成する方法
この手順では、受信を構成し、コンテンツ ベースのルーティング (CBR) シナリオでは、簡単な方法で主要な概念を説明するために場所を送信します。 ここで示す概念として公開されているオーケストレーションに適用できる、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]サービス。  

## <a name="prerequisites"></a>前提条件  
 この手順があることを前提としています。  

-   ように、machince.config ファイルが変更[BAM インターセプタ動作を Machine.config ファイルに追加する方法](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)します。  

-   WCF アダプターが BizTalk server に示すよう作成[BizTalk Server の WCF アダプターを作成する方法](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)します。  

### <a name="to-configure-the-receive-and-send-locations"></a>構成する受信場所と送信場所  

1. BizTalk 管理コンソールを開きます。 これを行うには、次のようにクリックします。**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリックし、 **BizTalk Server 管理**。  

2. BizTalk アプリケーションの受信場所 ノードを検索する、コンソール ツリーを展開します。 クリックして[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 をクリックして**アプリケーション**で選択したアプリケーションをクリックして、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスの種類 ダイアログ ボックスをクリック**受信場所**します。 ある、新しい受信場所を作成した 1 つに対応します。 無効の状態になります。  

3. 開く受信場所をダブルクリックして、**受信場所のプロパティ**] ダイアログ ボックスし、[Wcf-custom トランスポートの種類としてを選択します。  

4. をクリックして、**構成**ボタンをクリックする、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。  

5. をクリックして、**バインド**タブし、使用するバインディングを選択します。  

6. をクリックして、**動作** タブで、右クリックし、 **endpointbehavior**ノードをクリックして**拡張機能の追加**します。  

7. BAMEndPointExtension (machine.config ファイルに追加した拡張機能) を選択し、クリックして**Ok**します。  

    ![動作拡張機能の選択画面](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")  

8. 作成した拡張機能を選択、次の値を入力し、クリックして**OK**:  


   |      プロパティ      |                                                        値                                                         |
   |--------------------|----------------------------------------------------------------------------------------------------------------------|
   | Pollingintervalsec に |                                                          10                                                          |
   |  ConnectionString  | ConnectionString:Integrated Security = SSPI;Persist Security Info = False; Initial Catalog = BAMPrimaryImport; データ ソース = |


9. **受信場所のプロパティ**ダイアログ ボックスで、 **PassThruReceive**から、**受信パイプライン**ドロップダウン リスト、およびクリック **[ok]**.  

10. 受信場所を有効にして、管理コンソールを更新します。 開始状態では、セットアップが成功したことを示します。  

## <a name="see-also"></a>参照  
 [BAM データを受信するための WCF アダプターの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)