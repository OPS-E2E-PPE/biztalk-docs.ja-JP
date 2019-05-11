---
title: ポリシーをテストする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49c682645a534f43476244fcda26453944048168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383732"
---
# <a name="how-to-test-policies"></a>ポリシーをテストする方法
ポリシーをテストするには、ファクトがルールを実行できる必要があります。 ファクトを追加するには XML ドキュメントで値を指定またはファクトとして .NET オブジェクトの配列をエンジンに提供するには、ポリシー テスターをポイントはデータベース テーブルがファクト作成コンポーネントを使用できます。 詳細については、次を参照してください。[ファクト作成コンポーネントを作成する](../core/how-to-create-a-fact-creator.md)します。  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a>ビジネス ルール作成ツールでポリシーをテストするには  
  
1.  ポリシー エクスプ ローラー ウィンドウで、テストするポリシーのバージョンをクリックします。  
  
2.  をクリックして、**ポリシーのテスト**メニュー バーのボタン (緑色の矢印)。  
  
     上部のペインには、ポリシーのルールを参照するファクトの種類が表示されます。  
  
3.  ファクトのインスタンスを追加するには、クリックして、 **XML ドキュメント**または**データベース テーブル**ファクトの種類をクリック**インスタンスの追加**します。  
  
4.  ファクトのインスタンスを削除する場合、対応するファクトの種類をクリックします。 をクリック**インスタンスの削除**します。  
  
5.  記述したファクト作成コンポーネントを追加する場合は、クリックして**追加**ファクト作成コンポーネントのペインでします。  
  
6.  クリックして**テスト**します。  
  
     ポリシー テストのトレース出力は、テスト出力ウィンドウに表示されます。  
  
7.  保存、クリア、選択、出力ウィンドウで右クリックするか、出力のテキストをコピーします。  
  
     ![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")  
ポリシーをテストするファクトの選択