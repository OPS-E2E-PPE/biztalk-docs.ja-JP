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
# <a name="database-failover-support"></a><span data-ttu-id="9cdf3-102">データベース フェールオーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="9cdf3-102">Database Failover Support</span></span>
<span data-ttu-id="9cdf3-103">インスタンスを渡すことができます、 **PolicyFetchErrorHandler**のオーバー ロードされたコンス トラクターにパラメーターとしてデリゲート、**ポリシー**クラス。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-103">You can pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to overloaded constructors of the **Policy** class.</span></span> <span data-ttu-id="9cdf3-104">データベースからポリシー詳細をフェッチ中にエラーが発生したときに、デリゲート インスタンスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-104">When an error occurs while fetching the policy details from the database, the delegate instance is invoked.</span></span> <span data-ttu-id="9cdf3-105">トラップする try-catch ブロックを使用することもできます**RuleStoreConnectionException**と**RuleStoreCompatibilityException**ルール エンジンがルール エンジンへの接続に失敗したときに発生した例外。データベース。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-105">You can also use a try-catch block to trap **RuleStoreConnectionException** and **RuleStoreCompatibilityException** exceptions that are raised when the rule engine fails to connect to the Rule Engine database.</span></span>  
  
 <span data-ttu-id="9cdf3-106">インスタンスを渡さない場合、 **PolicyFetchErrorHandler**デリゲートのパラメーターとして、**ポリシー**コンス トラクター、または使用する場合、 **CallRules**図形に、オーケストレーション、しにエラーが発生、データベースからポリシー詳細をフェッチ中に次のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-106">If you do not pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to the **Policy** constructor, or if you use the **CallRules** shape in an orchestration, then if an error occurs while fetching the policy details from the database, the following events happen:</span></span>  
  
1.  <span data-ttu-id="9cdf3-107">ルール エンジンの値を使用して、 **PolicyFetchErrorHandlerAssembly**と**PolicyFetchErrorHandlerClass**の下にレジストリ エントリ**hkey_local_machine \software\microsoft\ ですBusinessRules\3.0**します。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-107">The rule engine uses the values of the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**.</span></span> <span data-ttu-id="9cdf3-108">既定値、 **PolicyFetchErrorHandlerAssembly**と**PolicyFetchErrorHandlerClass**レジストリ エントリは**Microsoft.BizTalk.RuleEngineExtensions**と**Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper**それぞれします。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-108">The default values for the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries are **Microsoft.BizTalk.RuleEngineExtensions** and **Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper** respectively.</span></span>  
  
2.  <span data-ttu-id="9cdf3-109">**ExceptionHelper**クラスが実装する、 **IPolicyFetchErrorMaker**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-109">The **ExceptionHelper** class implements the **IPolicyFetchErrorMaker** interface.</span></span>  
  
3.  <span data-ttu-id="9cdf3-110">ルール エンジンは、 **get_ErrorHandler**メソッドを**IPolicyFetchErrorMaker**エラー処理メソッドへのポインターを取得するためのインターフェイスし、これを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-110">The rule engine invokes the **get_ErrorHandler** method on the **IPolicyFetchErrorMaker** interface to get a pointer to the error-handling method and invokes it.</span></span>  
  
4.  <span data-ttu-id="9cdf3-111">既定のエラー処理メソッドを呼び出す、 **SetDBFailure**メソッドは BTSDBAccessor.dll で定義します。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-111">The default error-handling method invokes the **SetDBFailure** method, which is defined in BTSDBAccessor.dll.</span></span>  
  
5.  <span data-ttu-id="9cdf3-112">**SetDBFailure**メソッドにより、BizTalk サービスをシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-112">The **SetDBFailure** method causes the BizTalk service to shut down.</span></span> <span data-ttu-id="9cdf3-113">BizTalk サービスでは、1 分後に再起動し、データベースがまだ使用できない場合はシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-113">The BizTalk service restarts in one minute and shuts down if the databases are still not available.</span></span> <span data-ttu-id="9cdf3-114">このサイクルは、データベースが得られるまで繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="9cdf3-114">This cycle repeats until the databases are available.</span></span>