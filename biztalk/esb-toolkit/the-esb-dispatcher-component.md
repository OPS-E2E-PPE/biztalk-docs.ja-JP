---
title: "ESB ディスパッチャー コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85655b5f-4717-42d1-b005-0a5592d5653b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe377221034637eab23b70c50ccf48a8454a23bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-dispatcher-component"></a>ESB ディスパッチャー コンポーネント
Itinerary サービスのメッセージング ベース ESB ディスパッチャー コンポーネント内で実行されます。 ディスパッチャーのコンポーネントでは、送信メッセージのエンドポイントの場所のプロパティを動的に設定でき、メッセージを動的に変換することができます。  
  
## <a name="component-properties"></a>コンポーネント プロパティ  
 ディスパッチャーのコンポーネントには、6 つのプロパティがあります。  
  
-   **RoutingServiceName**です。 このプロパティは、メッセージ ベースのルーティング サービスの登録名を指定します。 既定値は**Microsoft.Practices.ESB.Services.Routing**です。  
  
-   **TransformServiceName**です。 このプロパティは、トランス フォームのメッセージング ベースのサービスの登録名を指定します。 既定値は**Microsoft.Practices.ESB.Services.Transform**です。  
  
-   **検証**です。 このプロパティは、メッセージが検証に使用する必要があるかどうかを指定します。  
  
-   **有効になっている**です。 このプロパティは、有効またはコンポーネントを無効にします。  
  
-   **エンドポイント**です。 このプロパティは、BizTalk ESB Toolkit に登録されている形式での競合回避モジュールの接続文字列です。  
  
-   **マップ名**です。 このプロパティは、マップの完全修飾名または接続文字列の形式に登録されている[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
    -   マップ名の例を次に示します。  
  
        ```  
        GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
        ```