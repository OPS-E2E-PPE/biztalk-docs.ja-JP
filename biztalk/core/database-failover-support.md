---
title: データベース フェールオーバー サポート |Microsoft ドキュメント
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
ms.openlocfilehash: 3bbc795191eb2c13ca35d55846719cebc20d61a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238634"
---
# <a name="database-failover-support"></a><span data-ttu-id="dff43-102">データベース フェールオーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="dff43-102">Database Failover Support</span></span>
<span data-ttu-id="dff43-103">インスタンスを渡すことができます、 **PolicyFetchErrorHandler**のオーバー ロードされたコンス トラクターにパラメーターとしてデリゲート、**ポリシー**クラスです。</span><span class="sxs-lookup"><span data-stu-id="dff43-103">You can pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to overloaded constructors of the **Policy** class.</span></span> <span data-ttu-id="dff43-104">データベースからポリシー詳細をフェッチしている間にエラーが発生した場合、デリゲート インスタンスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dff43-104">When an error occurs while fetching the policy details from the database, the delegate instance is invoked.</span></span> <span data-ttu-id="dff43-105">トラップする try-catch ブロックを使用することもできます**RuleStoreConnectionException**と**RuleStoreCompatibilityException**ルール エンジンがルール エンジンへの接続に失敗したときに発生する例外データベースです。</span><span class="sxs-lookup"><span data-stu-id="dff43-105">You can also use a try-catch block to trap **RuleStoreConnectionException** and **RuleStoreCompatibilityException** exceptions that are raised when the rule engine fails to connect to the Rule Engine database.</span></span>  
  
 <span data-ttu-id="dff43-106">インスタンスが渡されない場合、 **PolicyFetchErrorHandler**デリゲートのパラメーターとして、**ポリシー**コンス トラクター、または使用する場合、 **CallRules**図形に、オーケストレーション、し、エラーが発生した場合は、データベースからのポリシーの詳細をフェッチ中に、次のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="dff43-106">If you do not pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to the **Policy** constructor, or if you use the **CallRules** shape in an orchestration, then if an error occurs while fetching the policy details from the database, the following events happen:</span></span>  
  
1.  <span data-ttu-id="dff43-107">ルール エンジンの値を使用して、 **PolicyFetchErrorHandlerAssembly**と**PolicyFetchErrorHandlerClass**の下のレジストリ エントリ**hkey_local_machine \software\microsoft\BusinessRules\3.0**です。</span><span class="sxs-lookup"><span data-stu-id="dff43-107">The rule engine uses the values of the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**.</span></span> <span data-ttu-id="dff43-108">に対して、既定値、 **PolicyFetchErrorHandlerAssembly**と**PolicyFetchErrorHandlerClass**レジストリ エントリは**Microsoft.BizTalk.RuleEngineExtensions**と**Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper**それぞれします。</span><span class="sxs-lookup"><span data-stu-id="dff43-108">The default values for the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries are **Microsoft.BizTalk.RuleEngineExtensions** and **Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper** respectively.</span></span>  
  
2.  <span data-ttu-id="dff43-109">**ExceptionHelper**クラスが実装する、 **IPolicyFetchErrorMaker**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="dff43-109">The **ExceptionHelper** class implements the **IPolicyFetchErrorMaker** interface.</span></span>  
  
3.  <span data-ttu-id="dff43-110">ルール エンジン、 **get_ErrorHandler**メソッドを**IPolicyFetchErrorMaker**エラー処理メソッドへのポインターを取得するためのインターフェイスし、これを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dff43-110">The rule engine invokes the **get_ErrorHandler** method on the **IPolicyFetchErrorMaker** interface to get a pointer to the error-handling method and invokes it.</span></span>  
  
4.  <span data-ttu-id="dff43-111">既定のエラー処理メソッドを呼び出して、 **SetDBFailure** BTSDBAccessor.dll で定義されているメソッド。</span><span class="sxs-lookup"><span data-stu-id="dff43-111">The default error-handling method invokes the **SetDBFailure** method, which is defined in BTSDBAccessor.dll.</span></span>  
  
5.  <span data-ttu-id="dff43-112">**SetDBFailure**メソッドにより、BizTalk サービスをシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="dff43-112">The **SetDBFailure** method causes the BizTalk service to shut down.</span></span> <span data-ttu-id="dff43-113">BizTalk サービスは、1 分以内に再起動し、データベースがまだ使用できない場合はシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="dff43-113">The BizTalk service restarts in one minute and shuts down if the databases are still not available.</span></span> <span data-ttu-id="dff43-114">このサイクルは、データベースが使用できるようになるまで繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="dff43-114">This cycle repeats until the databases are available.</span></span>