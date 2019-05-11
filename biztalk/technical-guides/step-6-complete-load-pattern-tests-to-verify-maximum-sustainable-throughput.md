---
title: 手順 6:維持可能な最大のスループットを検証するための持続ロード パターン テストの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd790354-be9f-4278-bd15-493eac8970c9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28b482c6202741353987a28d4a943154a933abbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401214"
---
# <a name="step-6-perform-constant-load-pattern-tests-to-verify-maximum-sustainable-throughput"></a>手順 6:維持可能な最大のスループットを検証するための持続ロード パターン テストを実行します。
ロード Visual Studio 2010 を使用して、BizTalk Server ソリューションをテストするとき、」の説明に従って、概算最大持続可能なスループット (MST) のソリューションが決定したら、持続ロード パターン テストを実行する必要があります[手順 5。維持可能な最大のスループットを判断するステップ ロード パターン テストの実行](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)します。 これは、時間の経過と共に、MST が維持可能な実際にあることを確認し、今後は、BizTalk Server アプリケーションまたは環境に適用されるパフォーマンス チューニングの効果を評価する基準のロード テストを作成するために実行する必要があります。  
  
## <a name="create-and-run-a-constant-load-pattern-test"></a>作成し、一定のロード パターン テストの実行  
 "BTS_Messaging_"BTS_Messaging_Step.loadtest"ステップ ロード パターン テストを保存するだけでは、同じテスト ミックス、カウンター セット、およびステップ ロード パターン テストで使用されるカウンター セットの割り当てを使用する定数のロード パターン テストを作成する最も簡単な方法Constant.loadtest"と"BTS_Messaging_Constant.loadtest"をいくつか変更し、行います。 フォローされている定数のロード パターンを作成する手順をテストでは、既存のテストのステップ ロード パターンに基づきます。  
  
1.  開いていない場合は、BTS_Messaging_Step.loadtest を開きます。  
  
2.  をクリックして**ファイル**選択**LoadTests\BTS_Messaging_Step.loadtest に名前を付けて**します。  
  
3.  **ファイルに名前を付けて**] ダイアログ ボックスの横に**ファイル名**C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest を入力し、[クリックして**保存**します。  
  
4.  ロード テスト エディターで、シナリオの名前を変更**BTS_Messaging_Step**に**BTS_Messaging_Constant**します。 直下にあるシナリオの名前が表示されます、**シナリオ**フォルダー。  
  
5.  値のままに**テスト ミックス**と**ネットワーク ミックス**をクリックして選択が変更されていない**ステップ ロード パターン**します。  
  
6.  右クリック**ステップ ロード パターン**選択**プロパティ**します。  
  
7.  **プロパティ**セクションの**ロード パターン**横のドロップダウン リストをクリックして**パターン**からパターンを変更および**手順**に**定数**します。  
  
8.  **プロパティ**セクションの**パラメーター**の値を変更**持続ユーザー カウント**をユーザーの数よりも若干小さい値に、ステップ ロード パターンテストが大きすぎるになっていました (つまりの値、**数/秒あたりに受信した BizTalk:Messaging\Documents**が一貫しての値を超えるを開始した**BizTalk:Messaging\Documents 処理数/秒**の値、 **BizTalk:Message ボックス: 一般的な Counters\Spool サイズ**unbounded 増え始め)。  
  
9. **実行設定**フォルダーを右クリックし**Setting1 の実行 [Active]** 選択と**プロパティ**。  
  
10. プロパティの一覧をスクロールして、**タイミング**セクションの値を入力して**実行継続時間**少なくとも 10 分間の (00: 10:00) ことを確認しますの値は、**サンプル レート**5 秒に設定されているが (00: 00:05)。  
  
11. テスト名 (例: BTS_Messaging_Constant) を右クリックして、ロード テストを開始し、**テストの実行**メニュー オプション。