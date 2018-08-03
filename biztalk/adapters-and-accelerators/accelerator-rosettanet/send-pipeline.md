---
title: 送信パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58ca6a63-525a-4b16-932d-6d26e68f6fab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5700b3adb0769edff4ec820b4d95353383c08e6d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968019"
---
# <a name="send-pipeline"></a>送信パイプライン
このサンプルは、作業 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]送信パイプラインをアプリケーション用にカスタマイズできます。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルは、BTARN 送信パイプライン (PipelineSend.btp) を使用して、XML 送信メッセージを同等の RNIF メッセージに処理する方法を示します。 Pipelinesend.btp は*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines にあります。 このサンプルには次のステージが含まれます。  
  
-   XML アセンブラー  
  
-   MIME エンコーダー  
  
-   送信メッセージ否認不可  
  
> [!NOTE]
>  Visual Studio のパイプライン デザイナーで、上記の BTARN 送信パイプラインのコンポーネントのいずれかを選択しても、そのコンポーネントのプロパティは [プロパティ] ペインには表示されません。 コンポーネントのプロパティを表示する必要があります、コンポーネントを追加するツールボックスを使用して、 **[ツールボックス アイテムの**ツール] メニュー コマンド;、送信パイプラインから既存コンポーネントを削除してからコンポーネントを追加し、パイプライン デザイナーで適切なステージにツールボックスです。 コンポーネントを選択すると、そのコンポーネントのプロパティが [プロパティ] ペインに表示されます。  
  
 このパイプラインでは、このパイプライン内のメッセージ フローのコンポーネントに関する詳細については、次を参照してください。 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)します。  
  
## <a name="see-also"></a>参照  
 [パイプラインのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)