---
title: カスタム パイプライン コンポーネントの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom]
- pipeline components [custom], about pipeline components
- pipeline components [custom], creating
- customizing, pipeline components
- pipeline interfaces
- IDisassemblerComponent
- pipeline interfaces, about pipeline interfaces
- creating, pipeline components [custom]
- IAssemblerComponent
- IComponent
- pipeline components [custom], customizing
- pipeline interfaces, interface types
- pipeline components [custom], interfaces
- pipeline components [custom], component types
ms.assetid: cce61e0d-f1e3-4ec2-b38c-7c6eaf83ac10
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74828d31b55a4b50bdb18a537fbf7bb293445545
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008971"
---
# <a name="developing-custom-pipeline-components"></a>カスタム パイプライン コンポーネントの開発
ここでは、パイプライン コンポーネントを開発する方法について説明します。 3 種類のパイプライン コンポーネントを作成することができます: 全般、アセンブル、および逆アセンブルします。 これらの各パイプライン コンポーネントでは、プローブ機能を追加実装できます。 パイプライン コンポーネントの種類ごとに関連付けられているインターフェイスを BizTalk メッセージング エンジンに接続コンポーネントを実装する必要があります。コンポーネントの種類を識別するパイプライン インターフェイスは**IComponent**、 **IAssemblerComponent**、および**IDisassemblerComponent**します。 コンポーネントをプローブするには、実装する必要があります、 **IProbeMessage**インターフェイス。  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にはサンプル パイプライン コンポーネントが含まれており、独自のコンポーネントを作成するときに参照できます。 サンプル コンポーネントは、メッセージの末尾や先頭にデータを追加する方法を示すものです。 サンプル パイプライン コンポーネントの詳細については、次を参照してください。 [CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)します。  
  
> [!CAUTION]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、パイプラインからカスタム パイプライン コンポーネントを参照すると、コンパイル時エラーが発生することがあります。 このエラーを修正するには、コンパイル前にパイプライン デザイナーをいったん閉じて再度開きます。 または、コンポーネントをいったん削除して追加することもできます。  
> 
> [!IMPORTANT]
>  BizTalk Server にアップグレードする際、既存のカスタム パイプライン コンポーネント内の文字列変数には、"\n"などの改行文字が含まれていないことを確認します。 改行文字が含まれていると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でこのコンポーネントをコンパイルする際に "定数が 2 行目に続いています" エラーが発生します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パイプライン インターフェイスの使用](../core/using-pipeline-interfaces.md)  
  
-   [全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md)  
  
-   [アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md)  
  
-   [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)  
  
-   [プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md)  
  
-   
  [マネージド ストリーミング パイプライン コンポーネントでの Seek メソッドの実装](../core/implementing-a-seek-method-in-a-managed-streaming-pipeline-component.md)  
  
-   [解析エンジンおよびシリアル化エンジンの使用](../core/using-the-parsing-and-serializing-engines.md)  
  
-   [パイプライン コンポーネントからのエラーの報告](../core/reporting-errors-from-pipeline-components.md)  
  
-   [パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)  
  
-   [カスタム パイプラインのデバッグ](../core/debugging-custom-pipelines.md)