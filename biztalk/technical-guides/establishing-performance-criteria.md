---
title: パフォーマンス基準を確立する |Microsoft ドキュメント
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
ms.openlocfilehash: 5317445a5cf7e1e0b3fc07ab6ac301c764501460
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299986"
---
# <a name="establishing-performance-criteria"></a>パフォーマンス基準を確立します。
BizTalk Server ソリューションのパフォーマンスの目標は、通常、2 つのカテゴリ、スループットや待機時間のいずれかに分類されます。 このトピックでは、スループットや、BizTalk Server ソリューションの待機時間を評価するときに考慮すべき要因について説明します。  
  
> [!NOTE]  
>  多くの場合、スループットまたは BizTalk Server ソリューションの待機時間を最適化するには、競合している目標を表します。 たとえばを向上する可能性があります、バッチ サイズを増やすことで、ファイルのスループットの受信アダプターが、待機時間が短縮するとします。 このシナリオでは、アダプターはバッチ サイズを大きく、さらに、特定のメッセージのエンド ツー エンドの待機時間が減るのメッセージを蓄積する時間がかかります。  
  
## <a name="factors-affecting-throughput-of-a-biztalk-server-solution"></a>BizTalk Server ソリューションのスループットに影響する要因  
 **スループット**- BizTalk Server ソリューションで指定された時間間隔内で処理できるドキュメントの数として広く測定します。  
  
 スループットに影響する要因は次のとおりです。  
  
-   **メッセージのサイズ**– サイズの大きいメッセージがメッセージのマップに変換され、マッピング操作中に、ファイル システムにバッファリングするようにのに十分な場合に特に、小さいメッセージは、以上のオーバーヘッドを使用します。 メッセージのサイズが BizTalk Server のパフォーマンスに与える影響の詳細については、次を参照してください。[どのように BizTalk Server プロセス サイズの大きいメッセージ](http://go.microsoft.com/fwlink/?LinkId=139293)(http://go.microsoft.com/fwlink/?LinkId=139293)。  
  
-   **メッセージ形式**-2 つの主な形式を XML ファイルまたはフラット ファイルのいずれかで BizTalk Server にメッセージを受信します。 フラット ファイルは、BizTalk メッセージング エンジンによって処理される XML 形式に変換する必要があります、ため追加のオーバーヘッドがフラット ファイルの処理で発生します。  
  
-   **アダプターの要件**– 別のアダプターは、さまざまなパフォーマンス機能を多くの場合があります。 たとえば、MSDTC トランザクション サポートが必要なアダプターには、追加のオーバーヘッド/縮小と比べるとパフォーマンスを MSDTC トランザクションを使用しないアダプターは発生させます。 BizTalk ソリューションで使用されるアダプターは、取引先の要件や内部のビジネス ニーズに応じて異なります。  
  
-   **オーケストレーションの処理要件**– オーケストレーションがカプセル化するための優れた柔軟性を提供し、BizTalk で受信したメッセージをビジネス プロセスを適用します。 同時には、オーケストレーションは、BizTalk Server ソリューションのスループットを見積もる場合に考慮する必要がありますのオーバーヘッドを消費します。  
  
-   **ピーク負荷要件**– 測定規則的でドキュメント処理の大部分は必ずしも発生しません。 など、BizTalk Server ソリューションは、営業時間の終了時に、その処理負荷の大きな割合を維持することがあります。 したがってピーク負荷要件と、BizTalk Server ソリューションの最大持続可能なスループット (MST) 点を考慮してアカウントのスループットの条件を確立するときにします。 詳細については、BizTalk Server ソリューションの MST を測定を参照してください[測定最大エンジン スループット](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?。LinkID = 154388) および[維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID = 153815)。  
  
-   **ドキュメント追跡の要件**: ドキュメント追跡のオーバーヘッドは追加、システムにします。 ドキュメント追跡の要件は、BizTalk ソリューションのスループットの目標を見積もるときに、主要な考慮事項をする必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のパフォーマンスをテストする方法](../technical-guides/biztalk-server-performance-testing-methodology.md)