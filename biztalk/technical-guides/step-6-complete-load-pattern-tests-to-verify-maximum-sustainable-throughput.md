---
title: '手順 6: 最大スループットを検証するための持続ロード パターンのテストを実行します |Microsoft ドキュメント'
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
ms.openlocfilehash: b6bfc0b9670366ab2f38046fcdc5497234b51ba5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302098"
---
# <a name="step-6-perform-constant-load-pattern-tests-to-verify-maximum-sustainable-throughput"></a>手順 6: 最大スループットを検証するための持続ロード パターンのテストを実行します。
負荷を Visual Studio 2010 を使用して、BizTalk Server ソリューションをテストする場合、」の説明に従って、概算最大持続可能なスループット (MST) ソリューションが特定されると、持続ロード パターンのテストを実行する必要があります[手順 5: ステップ ロードの実行維持可能な最大のスループットを判断するテストのパターンを](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)です。 これは、時間の経過と共に、MST が維持可能なで実際にことを確認し、前進パフォーマンス調整を行う場合、BizTalk Server アプリケーションまたは環境へ適用の効果を評価する基準ロード テストを作成するために行う必要があります。  
  
## <a name="create-and-run-a-constant-load-pattern-test"></a>定数のロード パターン テスト作成および実行  
 "BTS_Messaging_ として"BTS_Messaging_Step.loadtest"ステップ ロード パターンのテストを保存するだけでは、同じテスト ミックス、カウンター セットとテストのステップ ロード パターンで使用されるカウンター セットの割り当てを使用する定数のロード パターンのテストを作成する最も簡単な方法Constant.loadtest"し、いくつか"BTS_Messaging_Constant.loadtest"に変更します。 定数のロード パターンを作成する手順はテストされているフォローは、既存のテストのステップ ロード パターンに基づきます。  
  
1.  既に開かれていない場合は、BTS_Messaging_Step.loadtest を開きます。  
  
2.  をクリックして**ファイル**選択**LoadTests\BTS_Messaging_Step.loadtest に名前を付けて**です。  
  
3.  **ファイルに名前を付けて**] ダイアログ ボックスで、**ファイル名**C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest を入力し、[クリックして**保存**です。  
  
4.  ロード テスト エディターで、シナリオの名前を変更**BTS_Messaging_Step**に**BTS_Messaging_Constant**です。 直下にあるシナリオの名前が表示されます、**シナリオ**フォルダーです。  
  
5.  値のままにして**テスト ミックス**と**ネットワーク ミックス**をクリックして選択が変更されていない**ステップ ロード パターン**です。  
  
6.  右クリック**ステップ ロード パターン**選択**プロパティ**です。  
  
7.  **プロパティ**セクションの [**ロード パターン**] の横にドロップダウン リストをクリックして**パターン**からパターンを変更および**手順**に**定数**です。  
  
8.  **プロパティ**セクションの **パラメーター**の値を変更**ユーザー数の定数**をユーザーの数よりも若干小さい値に、ステップ ロード パターンテストが容認できないほど大きくなりすぎない (つまり、値、**数/秒あたりに受信した BizTalk:Messaging\Documents**が一貫しての値を超えるを開始した**BizTalk:Messaging\Documents 処理数/秒**の値、 **BizTalk:Message ボックス: 一般的な Counters\Spool Size** unbounded やすくが開始されました)。  
  
9. 下にある、**実行設定**フォルダーを右クリックして**Setting1 の実行 [アクティブ]** を選択し、**プロパティ**です。  
  
10. プロパティの一覧をスクロールして、**タイミング**セクションし、値を入力**実行継続時間**少なくとも 10 分間の (00: 10:00) ことを確認の値は、**サンプル レート**5 秒に設定されている (00: 00:05)。  
  
11. テスト名 (例: BTS_Messaging_Constant) を右クリックして、ロード テストを開始し、**テストの実行**メニュー オプション。