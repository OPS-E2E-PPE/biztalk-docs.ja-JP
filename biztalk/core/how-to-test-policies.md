---
title: "ポリシーをテストする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7a0f8c0d63d14d5a529039a6e1c8af5b363cc9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-test-policies"></a>ポリシーをテストする方法
ポリシーをテストするには、ルールを実行するためのファクトが必要です。 XML ドキュメント、またはポリシー テスターで指定するデータベース テーブル内で値を指定することにより、ファクトを追加できます。また、ファクト作成コンポーネントを使用して、.NET オブジェクトの配列をファクトとしてエンジンに提供することもできます。 詳細については、次を参照してください。[ファクト作成コンポーネントを作成する](../core/how-to-create-a-fact-creator.md)です。  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a>ビジネス ルール作成ツールでポリシーをテストするには  
  
1.  [ポリシー エクスプローラー] ウィンドウで、テストするポリシーのバージョンをクリックします。  
  
2.  クリックして、**テスト ポリシー**メニュー バー ボタン (緑色の矢印)。  
  
     最上部のペインに、ポリシー ルールが参照するファクトの種類が表示されます。  
  
3.  ファクトのインスタンスを追加するには、クリックして、 **XML ドキュメント**または**データベース テーブル**ファクトの種類をクリックして**インスタンスの追加**です。  
  
4.  ファクトのインスタンスを削除する場合は、対応するファクトの種類をクリック**インスタンスの削除**です。  
  
5.  記述したファクト作成コンポーネントを追加する場合は、クリックして**追加**ファクト作成コンポーネントのペインでします。  
  
6.  をクリックして**テスト**です。  
  
     ポリシーのテストのトレース出力がテスト出力ウィンドウに表示されます。  
  
7.  出力テキストを保存、クリア、選択、またはコピーする場合は、出力ウィンドウ内で右クリックします。  
  
     ![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")  
ポリシーのテストのためのファクトの選択