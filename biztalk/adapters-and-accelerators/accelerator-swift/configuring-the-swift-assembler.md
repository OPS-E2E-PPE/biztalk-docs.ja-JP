---
title: "SWIFT アセンブラーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77d47b2b3ab687f2fd72242f4ddbbc68ae8530c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-the-swift-assembler"></a>SWIFT アセンブラーを構成します。
を呼び出すときは、SWIFT アセンブラーは、次のタスクを実行、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信パイプライン。  
  
-   動的にメッセージの種類を検出し、ドキュメント スキーマの解決  
  
-   SWIFT のフラット ファイル解析された XML にシリアル化します。  
  
 エンコード文字セット (たとえば、ASCII または Unicode エンコードを使用する場合など) のシリアル化された出力をエンコードするために使用されるを構成することができます。  
  
 SWIFT アセンブラーを使用するカスタム送信パイプラインの開発時に SWIFT アセンブラーを構成します。  
  
 BizTalk パイプライン デザイナでは、カスタム送信パイプラインの開発時に SWIFT アセンブラーを構成します。  
  
 カスタム送信パイプラインのアセンブル ステージに追加された後に SWIFT アセンブラーを構成するには、パイプライン デザイナー キャンバスに SWIFT アセンブラー コンポーネントを選択します。 SWIFT アセンブラーし、フォーカスを受け取るし、内のプロパティ ウィンドウを使用してその構成プロパティを設定することができます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]です。  
  
 利用可能な構成プロパティとその説明と使用方法の詳細のテーブルの場合、次を参照してください。 [SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)です。  
  
 SWIFT アセンブラーを使用して、さまざまなシナリオと構成プロパティの設定については、次を参照してください。 [SWIFT 逆アセンブラおよびアセンブラ扱う](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)です。  
  
 カスタム パイプラインのバイナリのコンパイル時に静的に構成設定をカスタム パイプラインに書き込みます。 そのため、配置時に構成プロパティを変更または時刻を実行することはできません。  
  
> [!NOTE]
>  構成、コンパイル、およびカスタム パイプラインをデプロイした後、再コンパイルして、カスタム パイプラインを再配置、構成の変更が必要です。  
  
 カスタム パイプラインを展開して作成、構築、については、BizTalk Server ヘルプを参照してください。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [SWIFT アセンブラーの構成プロパティ](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)