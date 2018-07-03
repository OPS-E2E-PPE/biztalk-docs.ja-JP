---
title: SWIFT アセンブラーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50c58ad000e465949229400128ce4c47da40806e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993667"
---
# <a name="configuring-the-swift-assembler"></a>SWIFT アセンブラーの構成
Microsoft で起動するときに、SWIFT アセンブラーが、次のタスクを実行します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信パイプライン。  
  
- 動的にメッセージの種類を検出し、ドキュメント スキーマの解決  
  
- SWIFT のフラット ファイル解析された XML にシリアル化します。  
  
  エンコードの文字 (たとえば、ASCII または Unicode エンコーディングを使用する場合など) のシリアル化された出力をエンコードするために使用される設定を構成できます。  
  
  SWIFT アセンブラーを使用するカスタム送信パイプラインの開発時に、SWIFT アセンブラーを構成します。  
  
  BizTalk パイプライン デザイナでは、カスタム送信パイプラインの開発時に、SWIFT アセンブラーを構成します。  
  
  カスタム送信パイプラインのアセンブル ステージに追加した後で、SWIFT アセンブラーを構成するには、パイプライン デザイナー キャンバスに SWIFT アセンブラー コンポーネントを選択します。 SWIFT アセンブラーし、フォーカスを受け取るし、Microsoft 内で [プロパティ] ウィンドウを使用してその構成プロパティを設定する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]します。  
  
  使用可能な構成プロパティとその説明および使用方法の詳細のテーブルの場合、次を参照してください。 [SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)します。  
  
  SWIFT アセンブラーを使用して、さまざまなシナリオと構成プロパティの設定については、次を参照してください。 [SWIFT 逆アセンブラーとアセンブラー](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)します。  
  
  カスタム パイプラインのバイナリがコンパイルされると、静的に構成設定をカスタム パイプラインに書き込みます。 そのため、デプロイ時に構成プロパティを変更したり、時間を実行したりすることはできません。  
  
> [!NOTE]
>  構成、コンパイル、およびカスタム パイプラインをデプロイ後に再コンパイルし、カスタム パイプラインの再展開構成の変更が必要です。  
  
 作成、構築、およびカスタム パイプラインを展開する方法については、BizTalk Server のヘルプを参照してください。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)