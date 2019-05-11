---
title: BizUnit テスト_ケースの段階 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed0e725f-2c52-43f7-ae30-343413a703c2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b67f9211c6525ca64afcd40d2155169af138026
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305507"
---
# <a name="stages-of-a-bizunit-test-case"></a>BizUnit テスト_ケースのステージ
BizUnit テスト_ケースは、3 つのステージで構成されます。**TestSetup**、 **TestExecution**、および**TestCleanup**します。 各ステージには、作業の 1 つの個別単位を実行する責任を持っている 1 つまたは複数のテスト ステップが含まれています。たとえば、 **FileCreateStep**特定のファイル名で指定した場所でファイルの作成を担当します。  BizUnit は、70 以上のテスト ステップが含まれていて、拡張機能により、フレームワークに簡単に追加する新しいテスト ステップも提供します。 フレームワークに新しい手順を追加する機能は、幅広いシナリオで使用するための BizUnit を使用します。 このトピックでは、さらに詳しく BizUnit テストの段階について説明します。  
  
## <a name="setup-stage"></a>セットアップの段階  
 このセットアップ ステージでは、テスト用プラットフォームを準備します。 たとえば、特定のテストを実行するには、ファイルは、テストの実際の実行の準備として、ファイル ドロップにコピーする必要があります。 クリーンアップするには、このステージは、任意のファイルの場所や、テストで使用されるデータベースのテーブルも使用できます。 BizUnit 内のすべてのステージでは、追加できるテスト ステップの数に制限がない、複雑なシナリオを処理するために必要な柔軟性を提供します。  
  
## <a name="execution-stage"></a>実行のステージ  
 実行段階では、テストが実際に実行します。 これは、検証するときは、システムの機能は実際にテストします。  
  
## <a name="cleanup-stage"></a>クリーンアップのステージ  
 クリーンアップ ステージは、テスト手順については、一貫性のあるテストを実行する前に、の状態をプラットフォームが返すコンテナーです。 この段階は、実行段階でエラーが発生した場合でも常に実行します。 プラットフォームを基盤に返される理由は、1 つのテスト_ケースが各テスト・ケースを自律的にテスト スイートの一部として実行されるように、別に干渉しないようにです。 BizUnit で効率的なテストの基本原則の 1 つは、この段階で、システムの完全なクリーンアップのことを確認します。  
  
 次の図は、3 つの段階でのテスト ステップを含む、サンプルのテスト ケースの形式を示しています。 セットアップ、実行、およびクリーンアップします。 BizUnit とテスト_ケースを定義するときに、この構造体を常に従うことが重要です。  
  
 ![BizUnit テストのステージ](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")  
BizUnit テストのステージ  
  
## <a name="see-also"></a>参照  
 [自動テストを容易にするための BizUnit の使用](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)