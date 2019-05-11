---
title: パイプライン コンポーネントの開発を逆アセンブル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDisassemblerComponent interface, disassembling
- pipeline components [custom], IDisassemblerComponent
- pipeline components [custom], IBaseComponent
- IBaseComponent interface, disassembling
- pipeline components [custom], disassembling
ms.assetid: 77c0aa7d-4d1b-4a8f-bef8-d38e7e4045c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00258b86f2da320b0ec13963a96a93aca8de477a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530925"
---
# <a name="developing-a-disassembling-pipeline-component"></a>逆アセンブラー パイプライン コンポーネントの開発
逆アセンブラー パイプライン コンポーネントは、入力に 1 つのメッセージを受け取り、出力で、0 個以上のメッセージが生成されます。 逆アセンブラー コンポーネントは、個別のドキュメントにメッセージのインターチェンジの分割に使用されます。 逆アセンブラー コンポーネントは、次のインターフェイスを実装する必要があります。  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- **IPersistPropertyBag します。** このインターフェイスは .NET Framework SDK ドキュメントを参照してください。  
  
  独自の逆アセンブラー コンポーネントを作成するには拡張することによって、 **FFDasmComp**または**XMLDasmComp**クラス。  
  
> [!WARNING]
>  カスタム逆アセンブラーを suspendqueue MessageDestination コンテキスト プロパティ設定は、作業の中断の Seek(0) をサポートするために、逆アセンブラーによって返されるストリーム必要があります。  
  
> [!NOTE]
>  カスタム パイプライン コンポーネントは、出力メッセージ用に、入力メッセージからその他のパーツをコピーする必要があります。 これはさらに、パイプラインで処理するためを保持します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パイプライン コンポーネントでの受信データ ストリームの処理](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [逆アセンブラー パイプライン コンポーネントでのエンコードの処理](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [フラット ファイル逆アセンブラー パイプライン コンポーネントの拡張](../core/extending-the-flat-file-disassembler-pipeline-component.md)