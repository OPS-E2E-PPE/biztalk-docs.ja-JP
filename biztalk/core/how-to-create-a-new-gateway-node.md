---
title: 新しいゲートウェイ ノードを作成する方法 |Microsoft Docs
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
ms.openlocfilehash: 5549317c45fbb431155eb3fab3e757c519956cc8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385576"
---
# <a name="how-to-create-a-new-gateway-node"></a>新しいゲートウェイ ノードを作成する方法
PeopleSoft Enterprise で新しいゲートウェイ ノードの構成を作成し、次の手順に従います。  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a>作成して新しいゲートウェイ ノードを構成するには  
  
1. Peoplesoft の左側のパネルでクリックして、**ノード定義**リンク。  
  
2. をクリックして、**新しい値を追加**タブ。  
  
3. **ノード名**フィールドに、入力`MSEXTERNAL`、 をクリックし、**追加**します。  
  
4. をクリックして、**ノード**タブをクリックし、次の情報を入力します。  
  
   1. **説明 :** ノードの説明を入力します。  
  
   2. **ノードの種類:** 選択**外部**します。  
  
   3. **ルーティングの種類:** 選択**暗黙的な**します。  
  
      ![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")  
  
5. をクリックして、**コネクタ**タブをクリックし、次の情報を入力します。  
  
   1. **ゲートウェイ ID:** 入力`LOCAL`します。  
  
   2. **コネクタ ID:** 入力`HTTPTARGET`します。  
  
      ![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")  
  
6. をクリックして、**ルックアップ**アイコン。  
  
7. **コネクタ ID**、クリックして、 **HTTPTARGET**リンク。  
  
    ![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")  
  
8. **プロパティ**タブで、次の情報を入力します。  
  
   1.  **ヘッダー:** 入力`Y`します。  
  
   2.  **[HTTPPROPERTY]:** 入力`POST`します。  
  
   3.  **[Primaryurl]:** IP アドレスと、ターゲット コンピューター (開発用コンピューター) のポートを入力します。  
  
   > [!NOTE]
   >  **受信ポート**以前に設定します。  
  
    ![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")  
  
## <a name="see-also"></a>参照  
 [PeopleSoft の HTTP ホストとポートを作成する](../core/creating-a-peoplesoft-http-host-and-port.md)