---
title: チェックリスト:運用準備のテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecdf2609-ba77-4756-a949-ab4e10c54313
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8903e3c8885c846cd6ce810281eeae48e30482c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242587"
---
# <a name="checklist-testing-operational-readiness"></a>チェックリスト:運用準備のテスト
運用準備のためのテストは、見落とされがちまたは最小限に抑えるだけが実行される重要な手順です。 任意のエンタープライズ レベル アプリケーションの重要な要件を徹底的にテストおよび開発したソリューションを使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]例外ではありません。 少なくとも、運用環境に BizTalk ソリューションを移行する前に次のテストを実行する必要があります。  


|                                                                                                                                                                                         手順                                                                                                                                                                                          |                                                  リファレンス                                                  |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                      単体テスト                                                                                                                                                                                      |                  [単体テストの実行](../technical-guides/performing-unit-testing.md)                  |
|                                                                                                                                                                                   機能テスト                                                                                                                                                                                   |            [機能テストの実行](../technical-guides/performing-functional-testing.md)            |
|                                                                                                                                                                             ボトルネック テストとチューニング                                                                                                                                                                              | [ボトルネック テストとチューニングの実行](../technical-guides/performing-bottleneck-testing-and-tuning.md) |
|                                                                                                                                                                 ロード テストとテストの最大持続可能スループット (MST)                                                                                                                                                                  |   [読み込みとスループット テストの実行](../technical-guides/performing-load-and-throughput-testing.md)   |
| 可用性テスト:<br /><br /> -個々 のハードウェア コンポーネントに障害をテストします。<br />-テスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]失敗します。<br />-クラスター ノードのフェールオーバーをテストします。<br />-の回復をテストする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL Server を使用してデータベースのログ配布します。 |          [可用性テストの実行](../technical-guides/performing-availability-testing.md)          |

## <a name="in-this-section"></a>このセクションの内容  

-   [単体テストの実行](../technical-guides/performing-unit-testing.md)  

-   [機能テストの実行](../technical-guides/performing-functional-testing.md)  

-   [ボトルネック テストとチューニングの実行](../technical-guides/performing-bottleneck-testing-and-tuning.md)  

-   [読み込みとスループット テストの実行](../technical-guides/performing-load-and-throughput-testing.md)  

-   [可用性テストの実行](../technical-guides/performing-availability-testing.md)  

-   [テスト用ツール](~/technical-guides/tools-for-testing.md)