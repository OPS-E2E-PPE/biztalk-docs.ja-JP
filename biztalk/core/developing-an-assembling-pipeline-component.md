---
title: パイプライン コンポーネントの開発、アセンブル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IComponentUI interface, assembling
- IBaseComponent interface, assembling
- pipeline interfaces, IBaseComponent
- pipeline components [custom], interfaces
- pipeline interfaces, IComponentUI
- IAssemblerComponent interface, assembling
- pipeline interfaces, IAssemblerComponent
- pipeline components [custom], assembling
ms.assetid: 2f85421d-2010-4a36-82b5-ea8016f8aa99
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff36bac9dc5f14048e7d448f912f72c243146b8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389434"
---
# <a name="developing-an-assembling-pipeline-component"></a>アセンブラー パイプライン コンポーネントの開発
アセンブラー パイプライン コンポーネントは、.NET または COM コンポーネントの入力に複数のメッセージを受信し、出力の 1 つのメッセージが生成されます。 アセンブラー コンポーネントは、メッセージのインターチェンジ バッチに個々 のドキュメントを収集するために使用されます。  
  
> [!NOTE]
>  アセンブリの機能は使用されていないため、常に、BizTalk Server は、コンポーネントの入力を 1 つのドキュメントを渡します。  
  
 アセンブラー コンポーネントは、次のインターフェイスを実装する必要があります。  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   **IPersistPropertyBag します。** このインターフェイスは .NET Framework SDK ドキュメントを参照してください。  
  
> [!NOTE]
>  カスタム パイプライン コンポーネントは、出力メッセージ用に、入力メッセージからその他のパーツをコピーする必要があります。 これはさらに、パイプラインで処理するためを保持します。  
  
## <a name="see-also"></a>参照  
 [全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md)   
 [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)   
 [プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md)   
 [パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)   
 [CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)