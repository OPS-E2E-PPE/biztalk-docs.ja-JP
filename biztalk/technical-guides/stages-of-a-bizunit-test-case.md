---
title: "BizUnit テスト ケースの段階 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed0e725f-2c52-43f7-ae30-343413a703c2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff435fd1c69118112b0121bf68b38ae3151885f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="stages-of-a-bizunit-test-case"></a>BizUnit テスト ケースの段階
各 BizUnit テスト ケースは、3 つのステージで構成されています: **TestSetup**、 **TestExecution**、および**TestCleanup**です。 各ステージには、作業の 1 つの個別単位を実行するは、1 つまたは複数のテスト ステップが含まれています。たとえば、 **FileCreateStep**は指定されたファイル名で指定した場所にファイルの作成を担当します。  BizUnit は、70 以上のテスト ステップが含まれていて、新しいフレームワークに容易に追加するテストの手順を実行できるようにする拡張機能も提供します。 新しいステップ フレームワークを追加する機能には、幅広いシナリオで使用するための BizUnit ができます。 このトピックでは、さらに詳しく BizUnit テストの段階について説明します。  
  
## <a name="setup-stage"></a>セットアップ ステージ  
 このセットアップ ステージでは、テストのプラットフォームを準備します。 たとえば、特定のテストを実行することができます、前に、ファイルは、テストの実際の実行の準備として、ファイル ドロップにコピーする必要があります。 任意のファイルの場所や、テストで使用されるデータベース テーブル クリーンアップするには、このステージを使用することもできます。 BizUnit 内のすべてのステージに追加できるテスト ステップの数に制限がない、複雑なシナリオを処理するために必要な柔軟性を提供します。  
  
## <a name="execution-stage"></a>実行のステージ  
 実行段階では、テストが実際に実行します。 これは、実際にテストが検証しているシステムの機能です。  
  
## <a name="cleanup-stage"></a>クリーンアップ ステージ  
 クリーンアップ ステージを返す、プラットフォーム、一貫した状態でテストを実行する前にテスト ステップのコンテナーです。 この段階が実行のステージでエラーが発生した場合でも常に実行されます。 プラットフォームを基盤に返される理由は、1 つのテスト_ケースの各テスト・ケースは、テスト スイートの一部として自律的に実行されるように、別に干渉することを防ぐためです。 この段階で、システムの完全なクリーンアップを確保すると、BizUnit で効果的なテストの基本原則の 1 つです。  
  
 次の図は、次の 3 つの段階的にテスト ステップを含むサンプル テスト ケースの形式: セットアップ、実行、およびクリーンアップします。 BizUnit を持つテスト_ケースを定義するときに、この構造体を常に従うことが重要であります。  
  
 ![BizUnit テストのステージ](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")  
BizUnit テストのステージ  
  
## <a name="see-also"></a>参照  
 [BizUnit を使用して自動テストを容易にするには](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)