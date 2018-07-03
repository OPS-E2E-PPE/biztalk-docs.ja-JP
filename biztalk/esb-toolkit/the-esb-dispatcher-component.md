---
title: ESB ディスパッチャー コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85655b5f-4717-42d1-b005-0a5592d5653b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16281ff49da6470212e9e8396a051270adf1eef7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982131"
---
# <a name="the-esb-dispatcher-component"></a>ESB ディスパッチャー コンポーネント
ESB ディスパッチャー コンポーネント内でメッセージング ベースのスケジュール サービスが実行されます。 ディスパッチャー コンポーネントでは、送信メッセージのエンドポイントの場所のプロパティを動的に設定でき、メッセージを動的に変換することができます。  
  
## <a name="component-properties"></a>コンポーネント プロパティ  
 ディスパッチャー コンポーネントでは、6 つのプロパティがあります。  
  
- **RoutingServiceName**します。 このプロパティは、メッセージング ベースのルーティング サービスの登録名を指定します。 既定値は**Microsoft.Practices.ESB.Services.Routing**します。  
  
- **TransformServiceName**します。 このプロパティは、変換のメッセージング ベースのサービスの登録名を指定します。 既定値は**Microsoft.Practices.ESB.Services.Transform**します。  
  
- **検証**です。 このプロパティは、メッセージを検証する必要かどうかを指定します。  
  
- **有効になっている**します。 このプロパティは、有効またはコンポーネントを無効にします。  
  
- **エンドポイント**します。 このプロパティは、BizTalk ESB Toolkit に登録されている形式での競合回避モジュールの接続文字列です。  
  
- **マップ名**します。 このプロパティは、マップの完全修飾名または接続文字列の形式に登録されている[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
  -   マップ名の例を次に示します。  
  
      ```  
      GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
      ```