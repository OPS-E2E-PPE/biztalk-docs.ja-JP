---
title: 送信パイプライン |Microsoft ドキュメント
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
ms.openlocfilehash: 1b7ee5ad712466df79a4e6961062ea56b73ad248
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964064"
---
# <a name="send-pipeline"></a>送信パイプライン
このサンプルは、独自のアプリケーション用にカスタマイズできる [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 送信パイプラインです。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルは、BTARN 送信パイプライン (PipelineSend.btp) を使用して、XML 送信メッセージを同等の RNIF メッセージに処理する方法を示します。 PipelineSend.btp にあります*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines です。 このサンプルには次のステージが含まれます。  
  
-   XML アセンブラー  
  
-   MIME エンコーダー  
  
-   送信メッセージ否認不可  
  
> [!NOTE]
>  Visual Studio のパイプライン デザイナーで、上記の BTARN 送信パイプラインのコンポーネントのいずれかを選択しても、そのコンポーネントのプロパティは [プロパティ] ペインには表示されません。 コンポーネントのプロパティを表示する必要があります、コンポーネントを追加する、ツールボックスを使用して、**ツールボックス アイテムの選択**ツール メニューにコマンド以外の場合は、送信パイプラインから既存のコンポーネントを削除しからのコンポーネントを追加しますパイプライン デザイナーで適切なステージにツールボックスします。 コンポーネントを選択すると、そのコンポーネントのプロパティが [プロパティ] ペインに表示されます。  
  
 このパイプラインおよびパイプライン内のメッセージ フローのコンポーネントに関する詳細については、次を参照してください。 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)です。  
  
## <a name="see-also"></a>参照  
 [パイプラインのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)