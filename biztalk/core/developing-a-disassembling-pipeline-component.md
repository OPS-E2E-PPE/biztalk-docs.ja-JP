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
ms.openlocfilehash: 843958cdfe00a9fc9d1a2c178cb85adfe4ffc8d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999723"
---
# <a name="developing-a-disassembling-pipeline-component"></a>逆アセンブラー パイプライン コンポーネントの開発
逆アセンブラー パイプライン コンポーネントは入力時に 1 通のメッセージを受け取り、出力時に 0 通以上のメッセージを生成します。 逆アセンブラー コンポーネントは、メッセージのインターチェンジを個別のドキュメントに分割するために使用されます。 逆アセンブラー コンポーネントは次のインターフェイスを実装する必要があります。  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- **IPersistPropertyBag します。** (このインターフェイスについては、.NET Framework SDK のドキュメントを参照してください)  
  
  独自の逆アセンブラー コンポーネントを作成するには拡張することによって、 **FFDasmComp**または**XMLDasmComp**クラス。  
  
> [!WARNING]
>  カスタム逆アセンブラーで MessageDestination コンテキスト プロパティを SuspendQueue に設定する場合、逆アセンブラーから返されるストリームでは保留が動作するように Seek(0) をサポートしている必要があります。  
  
> [!NOTE]
>  カスタム パイプライン コンポーネントでは入力メッセージの追加部分を出力メッセージにコピーする必要があります。 これにより、パイプラインでの後続の処理のために追加部分が保持されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パイプライン コンポーネントでの受信データ ストリームの処理](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [逆アセンブラー パイプライン コンポーネントでのエンコードの処理](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [フラット ファイル逆アセンブラー パイプライン コンポーネントの拡張](../core/extending-the-flat-file-disassembler-pipeline-component.md)