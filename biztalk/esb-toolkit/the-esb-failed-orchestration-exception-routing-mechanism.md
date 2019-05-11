---
title: Esb オーケストレーションの例外ルーティング メカニズム |Microsoft Docs
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
ms.openlocfilehash: 1da528a8af1b232f014a349afae292a7c0e319d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399816"
---
# <a name="the-esb-failed-orchestration-exception-routing-mechanism"></a>Esb オーケストレーションの例外ルーティング メカニズム
ESB 失敗オーケストレーションの例外ルーティング メカニズムは、次の機能を提供します。  
  
-   **アンビエント プロパティをキャプチャするエラー メッセージを作成します。** **CreateFaultMessage**メソッドには、オーケストレーションを含むエラー メッセージが生成されますサービス名とサービス インスタンス ID、現在アクティブなオーケストレーション図形のオーケストレーションをアプリケーションの名前。オーケストレーションを処理するサーバーの名前を展開します。 例外の日付と時刻 (UTC 形式)。 現在も暗黙的に追加**System.Exception**現在のオーケストレーション図形の例外ハンドラーで生成されたオブジェクト。  
  
-   **エラー メッセージをオーケストレーションの既存のメッセージを追加する**します。 **AddMessage**メソッドには、オーケストレーションのメッセージと、エラー メッセージ内のすべてのメッセージ コンテキスト プロパティの XLANG 設定が保持されます。  
  
-   **エラー メッセージに既存の例外オブジェクトを明示的に追加**します。 **SetFaultMsgException**メソッドとしてオブジェクトをシリアル化、 **System.Exception**とエラー メッセージではこれを保存します。  
  
-   **サブスクライバーで受信したエラー メッセージから、列挙型のないメッセージのコレクションを取得する**します。 **GetMessages**メソッドは、XLANG メッセージとして、失敗したオーケストレーションからすべての永続化されたメッセージを取得します。 各 XLANG メッセージに永続化された各メッセージのすべての元のコンテキスト プロパティを返します。  
  
-   **サブスクライバーで受信したエラー メッセージから、厳密に型指定の XLANG オーケストレーション メッセージを取得する**します。 **GetMessage**メソッドは、XLANG メッセージとしてエラー メッセージから特定の種類の永続化されたメッセージを取得します。 XLANG メッセージに永続化されたメッセージのすべての元のコンテキスト プロパティを返します。 取得もサポートしています、 **System.Exception**オブジェクトが失敗したオーケストレーションによって生成され、取得された保存される**System.Exception**フォールト メッセージからオブジェクト。