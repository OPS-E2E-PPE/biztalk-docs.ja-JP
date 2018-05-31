---
title: ESB には、オーケストレーションの例外のルーティング メカニズムが失敗しました |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa05f44b-7fb2-48fd-886d-c6d179904e6d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afda61ea19587b327f0fe773b150eeb8f88a4f7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295082"
---
# <a name="the-esb-failed-orchestration-exception-routing-mechanism"></a>ESB オーケストレーション例外ルーティング機構に失敗しました
ESB 失敗オーケストレーション例外ルーティング メカニズムは、次の機能を提供します。  
  
-   **アンビエント プロパティをキャプチャするエラー メッセージを作成します。** **CreateFaultMessage**メソッドには、オーケストレーションを含むエラー メッセージが生成されますサービス名とサービス インスタンス ID に、現在アクティブ化されたオーケストレーションの図形では、オーケストレーションが、アプリケーションの名前。展開されると、オーケストレーションを処理するサーバーの名前と例外の日付と時刻 (UTC 形式)。 現在も暗黙的に追加**System.Exception**現在のオーケストレーション図形の例外ハンドラーで生成されたオブジェクト。  
  
-   **エラー メッセージをオーケストレーションの既存のメッセージを追加する**です。 **AddMessage**メソッドには、オーケストレーション メッセージと、エラー メッセージ内のすべてのメッセージ コンテキスト プロパティの XLANG 設定が保持されます。  
  
-   **エラー メッセージに既存の例外オブジェクトを明示的に追加**です。 **SetFaultMsgException**メソッドとしてオブジェクトをシリアル化、 **System.Exception**し、エラー メッセージで保持します。  
  
-   **サブスクライバーで受信したエラー メッセージから、列挙型のないメッセージのコレクションを取得する**です。 **GetMessages**メソッドは、XLANG メッセージとして、失敗したオーケストレーションからすべての永続化されたメッセージを取得します。 各 XLANG メッセージに永続化された各メッセージのすべての元のコンテキスト プロパティを返します。  
  
-   **サブスクライバーで受信したエラー メッセージから、厳密に型指定の XLANG オーケストレーション メッセージを取得する**です。 **GetMessage**メソッドは、エラー メッセージを XLANG メッセージとしてから、特定の種類の永続化されたメッセージを取得します。 XLANG メッセージに永続化されたメッセージのすべての元のコンテキスト プロパティを返します。 検索もサポートしています、 **System.Exception**オブジェクトが失敗したオーケストレーションによって生成され、取得、永続化された**System.Exception**フォールト メッセージからのオブジェクト。