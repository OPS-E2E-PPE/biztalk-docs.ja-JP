---
title: "データベース フェールオーバー サポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09347fdd-2929-4ed9-b0d8-698508663ecd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bbc795191eb2c13ca35d55846719cebc20d61a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="database-failover-support"></a>データベース フェールオーバーのサポート
インスタンスを渡すことができます、 **PolicyFetchErrorHandler**のオーバー ロードされたコンス トラクターにパラメーターとしてデリゲート、**ポリシー**クラスです。 データベースからポリシー詳細をフェッチしている間にエラーが発生した場合、デリゲート インスタンスが呼び出されます。 トラップする try-catch ブロックを使用することもできます**RuleStoreConnectionException**と**RuleStoreCompatibilityException**ルール エンジンがルール エンジンへの接続に失敗したときに発生する例外データベースです。  
  
 インスタンスが渡されない場合、 **PolicyFetchErrorHandler**デリゲートのパラメーターとして、**ポリシー**コンス トラクター、または使用する場合、 **CallRules**図形に、オーケストレーション、し、エラーが発生した場合は、データベースからのポリシーの詳細をフェッチ中に、次のイベントが発生します。  
  
1.  ルール エンジンの値を使用して、 **PolicyFetchErrorHandlerAssembly**と**PolicyFetchErrorHandlerClass**の下のレジストリ エントリ**hkey_local_machine \software\microsoft\BusinessRules\3.0**です。 に対して、既定値、 **PolicyFetchErrorHandlerAssembly**と**PolicyFetchErrorHandlerClass**レジストリ エントリは**Microsoft.BizTalk.RuleEngineExtensions**と**Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper**それぞれします。  
  
2.  **ExceptionHelper**クラスが実装する、 **IPolicyFetchErrorMaker**インターフェイスです。  
  
3.  ルール エンジン、 **get_ErrorHandler**メソッドを**IPolicyFetchErrorMaker**エラー処理メソッドへのポインターを取得するためのインターフェイスし、これを呼び出します。  
  
4.  既定のエラー処理メソッドを呼び出して、 **SetDBFailure** BTSDBAccessor.dll で定義されているメソッド。  
  
5.  **SetDBFailure**メソッドにより、BizTalk サービスをシャット ダウンします。 BizTalk サービスは、1 分以内に再起動し、データベースがまだ使用できない場合はシャットダウンします。 このサイクルは、データベースが使用できるようになるまで繰り返されます。