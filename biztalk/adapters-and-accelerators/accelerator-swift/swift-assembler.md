---
title: SWIFT アセンブラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler
- send pipelines, messages
- messages, send pipelines
ms.assetid: 2a95c7d4-da10-4058-bc2c-3efc35958e14
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f89720a36c026fa0e8f02902a8fefb08fcebf9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973315"
---
# <a name="swift-assembler"></a>SWIFT アセンブラー
送信の送信パイプラインによって送信されるすべてのメッセージの処理、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーション (送信ポートを通じて送信されます)。  
  
 送信処理に関連する論理実行段階では、BizTalk 送信パイプラインを構成します。 パイプライン コンポーネントは、サービスまたは各ステージを実装します。 具体的には、アセンブラーは、受信パイプラインのアセンブル ステージをサービスします。 A4SWIFT は、SWIFT 固有送信メッセージの処理、カスタムのアセンブラー コンポーネントで機能を提供します。  
  
 SWIFT アセンブラー、独自のフラット ファイル アセンブラーは、送信の SWIFT メッセージを処理するための機能を提供し、次の関数を実行します。  
  
- 動的にメッセージの種類を検出し、ドキュメント スキーマの解決  
  
- SWIFT のフラット ファイル解析された XML にシリアル化します。  
  
  次の図に、SWIFT アセンブラーのデータ フローです。  
  
  ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
  SWIFT アセンブラーの詳細については、[SWIFT 逆アセンブラーとアセンブラー](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for SWIFT ランタイム](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)