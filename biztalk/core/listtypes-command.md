---
title: ListTypes コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94febe8a-4c1e-4581-a6d1-ef579633e745
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda39d682bfb4649fc22afd892dd13849bfd1b09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380725"
---
# <a name="listtypes-command"></a>ListTypes コマンド
追加できる成果物の種類のすべてを一覧表示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、 **AddResource**コマンド。 詳細については、 **AddResource**コマンドを参照してください[AddResource コマンド](../core/addresource-command.md)します。  
  
 サポートされている成果物の種類の完全修飾名は次のとおりです。  
  
-   .NET アセンブリ:System.BizTalk:Assembly  
  
-   BAM 定義:System.BizTalk:Bam  
  
-   BizTalk アセンブリ:System.BizTalk:BizTalkAssembly  
  
-   BizTalk バインド ファイル:System.BizTalk:BizTalkBinding  
  
-   セキュリティ証明書:System.BizTalk:Certificate  
  
-   COM コンポーネント:System.BizTalk:Com  
  
-   アドホック ファイル:System.BizTalk:File  
  
-   処理後のスクリプト:System.BizTalk:PostProcessingScript  
  
-   処理前のスクリプト:System.BizTalk:PreProcessingScript  
  
-   ポリシーまたはルール:System.BizTalk:Rules  
  
-   仮想ディレクトリ:System.BizTalk:WebDirectory  
  
> [!NOTE]
>  名前空間の競合を避けるためには、型名のみ (アセンブリ) などではなく、完全な型名 (System.BizTalk:Assembly) などを常に使用する必要があります。  
  
## <a name="usage"></a>使用方法  
 **BTSTask ListTypes**  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)