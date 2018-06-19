---
title: ListTypes コマンド |Microsoft ドキュメント
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
ms.openlocfilehash: afe2519fc5507ae0975d050a998faec78f2940a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262218"
---
# <a name="listtypes-command"></a>ListTypes コマンド
追加できるアイテムの種類のすべてを一覧表示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、 **AddResource**コマンド。 詳細については、 **AddResource**コマンドを参照してください[AddResource コマンド](../core/addresource-command.md)です。  
  
 サポートされているアイテムの種類の完全修飾名は次のとおりです。  
  
-   .NET アセンブリ: System.BizTalk:Assembly  
  
-   BAM 定義: System.BizTalk:Bam  
  
-   BizTalk アセンブリ: System.BizTalk:BizTalkAssembly  
  
-   BizTalk バインド ファイル: System.BizTalk:BizTalkBinding  
  
-   セキュリティ証明書: System.BizTalk:Certificate  
  
-   COM コンポーネント: System.BizTalk:Com  
  
-   アドホック ファイル: System.BizTalk:File  
  
-   処理後のスクリプト: System.BizTalk:PostProcessingScript  
  
-   スクリプトを前処理: System.BizTalk:PreProcessingScript  
  
-   ポリシーまたはルール: System.BizTalk:Rules  
  
-   仮想ディレクトリ: System.BizTalk:WebDirectory  
  
> [!NOTE]
>  名前空間の競合を防ぐため、単独の型名 (Assembly など) ではなく、完全な型名 (System.BizTalk:Assembly) を使用するようにしてください。  
  
## <a name="usage"></a>使用方法  
 **BTSTask ListTypes**  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)