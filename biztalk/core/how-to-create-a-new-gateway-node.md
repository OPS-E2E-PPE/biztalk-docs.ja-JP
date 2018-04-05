---
title: 新しいゲートウェイ ノードを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- gateway nodes, creating
ms.assetid: e7c5f9a7-a58e-4661-9cb5-2414e31a57a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b371243d58389415349d5a88c05b7bf312e70ef9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-new-gateway-node"></a>新しいゲートウェイ ノードを作成する方法
PeopleSoft Enterprise に新しいゲートウェイ ノードを作成して構成するには、次の手順を実行します。  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a>新しいゲートウェイ ノードを作成および構成するには  
  
1.  Peoplesoft の左側のパネルでをクリックして、**ノード定義**リンクします。  
  
2.  クリックして、**新しい値を追加**タブです。  
  
3.  **ノード名**フィールドに「 `MSEXTERNAL`、クリックしてして**追加**です。  
  
4.  クリックして、**ノード**タブをクリックし、次の情報を入力します。  
  
    1.  **説明:**ノードの説明を入力します。  
  
    2.  **ノード型:**選択**外部**です。  
  
    3.  **ルーティングの種類:**選択**暗黙**です。  
  
     ![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")  
  
5.  クリックして、**コネクタ**タブをクリックし、次の情報を入力します。  
  
    1.  **ゲートウェイ ID:**入力`LOCAL`です。  
  
    2.  **コネクタ ID:**入力`HTTPTARGET`です。  
  
     ![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")  
  
6.  クリックして、**ルックアップ**アイコン。  
  
7.  **コネクタ ID**をクリックして、 **HTTPTARGET**リンクします。  
  
     ![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")  
  
8.  **プロパティ** タブで、次の情報を入力します。  
  
    1.  **ヘッダー:**入力`Y`です。  
  
    2.  **HTTPPROPERTY:**入力`POST`です。  
  
    3.  **[Primaryurl]:**ターゲット コンピューター (開発用コンピューター) のポートと IP アドレスを入力します。  
  
    > [!NOTE]
    >  **受信ポート**以前に設定します。  
  
     ![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")  
  
## <a name="see-also"></a>参照  
 [PeopleSoft HTTP ホストおよびポートを作成します。](../core/creating-a-peoplesoft-http-host-and-port.md)