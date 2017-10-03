---
title: "SWIFT アセンブラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembler
- send pipelines, messages
- messages, send pipelines
ms.assetid: 2a95c7d4-da10-4058-bc2c-3efc35958e14
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91d9411cce90079e8a84fc6919bd6ebf8b2b4371
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-assembler"></a>SWIFT アセンブラー
出力方向の送信パイプラインによって送信されるすべてのメッセージの処理、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーション (送信ポートを通じて送信されます)。  
  
 送信処理に関連する論理実行段階は、BizTalk 送信パイプラインを構成します。 パイプライン コンポーネントは、サービスまたは、各ステージを実装します。 具体的には、アセンブラーは、受信パイプラインのアセンブル ステージをサービスします。 A4SWIFT は、SWIFT に固有の送信メッセージがカスタムのアセンブラー コンポーネントで処理機能を提供します。  
  
 SWIFT のアセンブラーは、カスタムのフラット ファイル アセンブラーでは、送信 SWIFT メッセージの処理に機能を提供し、次の機能を実行します。  
  
-   動的にメッセージの種類を検出し、ドキュメント スキーマの解決  
  
-   SWIFT のフラット ファイル解析された XML にシリアル化します。  
  
 次の図は、SWIFT アセンブラー データ フローです。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
 SWIFT アセンブラーの詳細については、次を参照してください。 [SWIFT 逆アセンブラおよびアセンブラ扱う](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for SWIFT のランタイム](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)