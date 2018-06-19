---
title: '手順 1: 構成ファイルの受信場所 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df591263-964a-4ad8-bc3a-a553de8dae4f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78f8bccc187bf310b8426fc3d5fee36add44a9f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278258"
---
# <a name="step-1-configure-a-file-receive-location"></a>手順 1: 構成ファイルの受信場所
このトピックでは、送信ポートを呼び出すためにファイル フォルダーにドロップするダミーの要求メッセージを処理する FILE 受信場所を構成します。  
  
> [!NOTE]
>  このチュートリアルの手順は、既定のアプリケーションを使用することを想定しています (**BizTalk アプリケーション 1**)、ソリューションを作成します。 別のアプリケーションを作成して、そのアプリケーションで同じステップを実行することもできます。  
  
### <a name="to-configure-a-file-receive-location"></a>FILE 受信場所を構成するには  
  
1.  BizTalk Server 管理コンソールから下にある、 **BizTalk アプリケーション 1**  ノードを右クリックして**受信ポート**、 をポイント**新規**、順にクリック**一方向受信ポート**です。  
  
2.  [全般] タブには、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**ReceivePortRestAzureMarketPlace**です。|  
    |**失敗したメッセージのルーティングを有効にします。**|(選択解除)|  
  
3.  をクリックして**受信場所**、クリックして**新規**です。  
  
4.  [Receive Location1 - 受信場所のプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**ReceiveLocationAzureMarketPlace**です。|  
    |**型**|選択**ファイル**です。|  
    |**受信ハンドラー**|[ **BizTalkServerApplication**] を選択します。|  
    |**受信パイプライン**|選択**PassThruReceive**です。|  
  
5.  をクリックして**構成**です。  
  
6.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|ダミーの要求メッセージをドロップする場所を入力します。|  
    |**ファイル名**|保持します。`*.xml`|  
  
7.  をクリックして**OK**すべてのダイアログ ボックスを終了するまでです。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)