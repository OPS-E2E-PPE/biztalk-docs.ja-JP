---
title: パフォーマンス条件の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 181011d1-aa74-43fe-b05a-30b043956d70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6cd5c7b733ec85eb08acdc506d816d1a3fb1ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305669"
---
# <a name="establishing-performance-criteria"></a>パフォーマンス条件の設定
BizTalk Server ソリューションのパフォーマンスの目標は、通常、2 つのカテゴリ、スループットまたは待機時間のいずれかに分類されます。 このトピックでは、スループットまたは BizTalk Server ソリューションの待機時間を評価するときに考慮すべき要因について説明します。  
  
> [!NOTE]  
>  多くの場合、スループットまたは BizTalk Server ソリューションの待機時間を最適化するには、目標が矛盾するを表します。 向上させることが、バッチ サイズを増やすことで、ファイルのスループットの受信アダプターが、待機時間が短縮するとします。 このシナリオでは、アダプターが、特定のメッセージのエンド ツー エンドの待機時間がさらに削減されます、大きいバッチ サイズのメッセージを蓄積する時間がかかります。  
  
## <a name="factors-affecting-throughput-of-a-biztalk-server-solution"></a>BizTalk Server ソリューションのスループットに影響する要因  
 **スループット**- BizTalk Server ソリューションは、指定された時間間隔内で処理できるドキュメントの数として広く測定します。  
  
 スループットに影響する要因は次のとおりです。  
  
-   **メッセージ サイズ**– メッセージ マップに変換され、マッピング操作中に、ファイル システムにバッファリングするように、十分な大きさが場合に特にサイズの大きいメッセージが小さいメッセージより多くのオーバーヘッドを消費します。 メッセージのサイズが BizTalk Server のパフォーマンスに与える影響の詳細については、次を参照してください。[どのように BizTalk Server プロセス サイズの大きいメッセージ](http://go.microsoft.com/fwlink/?LinkId=139293)(http://go.microsoft.com/fwlink/?LinkId=139293)します。  
  
-   **メッセージ形式**-2 つの主な形式、XML ファイルまたはフラット ファイルのいずれかで BizTalk Server にメッセージを受信します。 フラット ファイルは、BizTalk メッセージング エンジンによって処理される XML 形式に変換する必要があります、ために、フラット ファイルの処理によって追加のオーバーヘッドが発生します。  
  
-   **アダプターの要件**– 別のアダプターは、さまざまなパフォーマンス機能を頻繁があります。 たとえば、MSDTC トランザクション サポートが必要なアダプターでは、MSDTC トランザクションを使用しないアダプターと比較して、追加のオーバーヘッド削減/パフォーマンスが発生します。 BizTalk ソリューションで使用されるアダプターは、取引先パートナーの要件や内部のビジネス ニーズに応じて異なります。  
  
-   **オーケストレーションの処理要件**: オーケストレーションがカプセル化するための優れた柔軟性を提供し、BizTalk で受信したメッセージにビジネス プロセスを適用します。 同時に、オーケストレーションは、オーバーヘッドで、BizTalk Server ソリューションのスループットを推定する際に考慮する必要を使用します。  
  
-   **ピーク負荷要件**– 測定規則的でドキュメント処理の大部分は必ずしも発生しません。 など、BizTalk Server ソリューションは、営業日の終了時に、その処理負荷の大きな割合を維持する可能性があります。 したがってピーク負荷要件と、BizTalk Server ソリューションの最大持続可能なスループット (MST) が考慮するスループットの条件を確立するときにします。 BizTalk Server ソリューションの MST を測定する詳細については、次を参照してください[最大持続可能なエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)と[を測定する最大の追跡スループット](http://go.microsoft.com/fwlink/?LinkID=153815)。 (http://go.microsoft.com/fwlink/?LinkID=153815).  
  
-   **ドキュメント追跡の要件**– ドキュメントの追跡は、システムで追加のオーバーヘッドを適用します。 ドキュメント追跡の要件は、BizTalk ソリューションのスループット目標を推定するときに、主要な考慮事項にすることがあります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のパフォーマンス テスト手法](../technical-guides/biztalk-server-performance-testing-methodology.md)