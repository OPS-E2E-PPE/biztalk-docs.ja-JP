---
title: データベース フェールオーバーのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09347fdd-2929-4ed9-b0d8-698508663ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774976e245d8b7ae72d8b10807a4166aa36e3d74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352617"
---
# <a name="database-failover-support"></a>データベース フェールオーバーのサポート
インスタンスを渡すことができます、 **PolicyFetchErrorHandler**のオーバー ロードされたコンス トラクターにパラメーターとしてデリゲート、**ポリシー**クラス。 データベースからポリシー詳細をフェッチ中にエラーが発生したときに、デリゲート インスタンスが呼び出されます。 トラップする try-catch ブロックを使用することもできます**RuleStoreConnectionException**と**RuleStoreCompatibilityException**ルール エンジンがルール エンジンへの接続に失敗したときに発生した例外。データベース。  
  
 インスタンスを渡さない場合、 **PolicyFetchErrorHandler**デリゲートのパラメーターとして、**ポリシー**コンス トラクター、または使用する場合、 **CallRules**図形に、オーケストレーション、しにエラーが発生、データベースからポリシー詳細をフェッチ中に次のイベントが発生します。  
  
1.  ルール エンジンの値を使用して、 **PolicyFetchErrorHandlerAssembly**と**PolicyFetchErrorHandlerClass**の下にレジストリ エントリ**hkey_local_machine \software\microsoft\ ですBusinessRules\3.0**します。 既定値、 **PolicyFetchErrorHandlerAssembly**と**PolicyFetchErrorHandlerClass**レジストリ エントリは**Microsoft.BizTalk.RuleEngineExtensions**と**Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper**それぞれします。  
  
2.  **ExceptionHelper**クラスが実装する、 **IPolicyFetchErrorMaker**インターフェイス。  
  
3.  ルール エンジンは、 **get_ErrorHandler**メソッドを**IPolicyFetchErrorMaker**エラー処理メソッドへのポインターを取得するためのインターフェイスし、これを呼び出します。  
  
4.  既定のエラー処理メソッドを呼び出す、 **SetDBFailure**メソッドは BTSDBAccessor.dll で定義します。  
  
5.  **SetDBFailure**メソッドにより、BizTalk サービスをシャット ダウンします。 BizTalk サービスでは、1 分後に再起動し、データベースがまだ使用できない場合はシャット ダウンします。 このサイクルは、データベースが得られるまで繰り返されます。