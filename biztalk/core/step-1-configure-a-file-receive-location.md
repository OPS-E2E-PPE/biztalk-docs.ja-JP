---
title: 手順 1:ファイルを構成する受信場所 |Microsoft Docs
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
ms.openlocfilehash: 2ae1bb74c162a0a61521392fc4cd75e99ba26297
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392826"
---
# <a name="step-1-configure-a-file-receive-location"></a>手順 1:ファイルを構成する受信場所
このトピックでは、ファイルを構成する送信ポートを呼び出すためにファイル フォルダーにドロップするダミー要求メッセージを使用する受信場所。  
  
> [!NOTE]
>  このチュートリアルの手順では、既定のアプリケーションを使用することを想定しています (**BizTalk アプリケーション 1**) ソリューションを作成します。 また別のアプリケーションを作成し、そのアプリケーションで同じ手順を実行できます。  
  
### <a name="to-configure-a-file-receive-location"></a>ファイル受信場所を構成するには  
  
1.  BizTalk Server 管理コンソールから下、 **BizTalk アプリケーション 1**ノードを右クリックして**受信ポート**、 をポイント**新規**、順にクリックします**一方向受信ポート**します。  
  
2.  [全般] タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**ReceivePortRestAzureMarketPlace**します。|  
    |**失敗したメッセージのルーティングを有効にします。**|(選択解除)|  
  
3.  クリックして**受信場所**、 をクリックし、**新規**します。  
  
4.  [Receive Location1 - 受信場所のプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**ReceiveLocationAzureMarketPlace**します。|  
    |**型**|選択**ファイル**します。|  
    |**受信ハンドラー**|**[BizTalkServerApplication]** を選択します。|  
    |**受信パイプライン**|選択**PassThruReceive**です。|  
  
5.  をクリックして**構成**です。  
  
6.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|ダミー要求メッセージをドロップする場所の場所を入力します。|  
    |**[ファイル名]**|保持 `*.xml`|  
  
7.  クリックして**OK**すべてのダイアログ ボックスを終了するまでです。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 5:BizTalk Server を使用して REST インターフェイスの呼び出し](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)