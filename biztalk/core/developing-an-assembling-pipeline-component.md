---
title: パイプライン コンポーネントの開発、アセンブル |Microsoft ドキュメント
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
ms.openlocfilehash: 8de06a815e1c5a6bf71700ad373ae3f278b3a9a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239618"
---
# <a name="developing-an-assembling-pipeline-component"></a>アセンブラー パイプライン コンポーネントの開発
アセンブラー パイプライン コンポーネントは、入力時に複数のメッセージを受け取り、出力時に 1 通のメッセージを生成する .NET または COM コンポーネントです。 アセンブラー コンポーネントは、個別のドキュメントをまとめてメッセージ インターチェンジのバッチを作成するために使用されます。  
  
> [!NOTE]
>  アセンブリ機能は使用されていないため、BizTalk Server は常に 1 つのドキュメントをコンポーネントの入力として渡します。  
  
 アセンブラー コンポーネントは次のインターフェイスを実装する必要があります。  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   **IPersistPropertyBag です。** (このインターフェイスについては、.NET Framework SDK のドキュメントを参照してください)  
  
> [!NOTE]
>  カスタム パイプライン コンポーネントでは入力メッセージの追加部分を出力メッセージにコピーする必要があります。 これにより、パイプラインでの後続の処理のために追加部分が保持されます。  
  
## <a name="see-also"></a>参照  
 [全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md)   
 [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)   
 [プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md)   
 [パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)   
 [CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)