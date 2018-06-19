---
title: サンプル操作エラー ハンドラ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ops adapters, error handler
- process management solution tutorial, Ops adapters
ms.assetid: e6c55f01-c004-4340-beaa-d77764ae34c1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93536733c884b4d5db57ba18619ebabdead17561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279626"
---
# <a name="the-sample-operations-error-handler"></a><span data-ttu-id="bbcb1-102">サンプル操作エラー ハンドラ</span><span class="sxs-lookup"><span data-stu-id="bbcb1-102">The Sample Operations Error Handler</span></span>
<span data-ttu-id="bbcb1-103">サンプル操作エラー ハンドラが 3 つの主要なアセンブリ: **OperationsClient**、 **OperationsHandler**、および**OperationsServer**です。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-103">The sample operations error handler has three major assemblies: **OperationsClient**, **OperationsHandler**, and **OperationsServer**.</span></span>  
  
 <span data-ttu-id="bbcb1-104">ソリューションを使用するアダプターの構成、 **OpsClient**内のオブジェクト、 **OperationsClient**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-104">The solution configures the adapter to use the **OpsClient** object in the **OperationsClient** assembly.</span></span> <span data-ttu-id="bbcb1-105">予想できるように、 **OpsClient**オブジェクトを実装して、 **IOpsAIC**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-105">As you'd expect, the **OpsClient** object implements the **IOpsAIC** interface.</span></span>  
  
 <span data-ttu-id="bbcb1-106">**OpsClient**オブジェクトが使用、 **IOperationsSystem**インターフェイスを呼び出す、 **OpsHandler**オブジェクトを介して、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]リモート処理機能します。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-106">The **OpsClient** object uses the **IOperationsSystem** interface to call the **OpsHandler** object through the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] remoting feature.</span></span> <span data-ttu-id="bbcb1-107">**IOperationsSystem**インターフェイスが次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-107">The **IOperationsSystem** interface appears as follows:</span></span>  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 <span data-ttu-id="bbcb1-108">**OperationsServer**、コンソール アプリケーションの要求を受信、 **OpsHandler**オブジェクトし、サーバーの役割を果たします、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]リモート処理機能します。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-108">The **OperationsServer**, a console application, listens for requests for the **OpsHandler** object and acts as the server for the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] remoting feature.</span></span> <span data-ttu-id="bbcb1-109">呼び出す、 **Execute**のメソッド、 **OpsClient**オブジェクトを呼び出す、 **Post**のメソッド、 **OpsHandler**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-109">Calling the **Execute** method of the **OpsClient** object in turn invokes the **Post** method of the **OpsHandler** object.</span></span>  
  
 <span data-ttu-id="bbcb1-110">**OpsHandler**メソッドが応答を使用して、引数文字列を記述して、**トレース**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-110">The **OpsHandler** methods respond by writing out their argument strings using the **Trace** object.</span></span> <span data-ttu-id="bbcb1-111">これによりコンソールにエラーが送信されます。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-111">This posts the errors to the console.</span></span> <span data-ttu-id="bbcb1-112">詳細については、**トレース**オブジェクト「Trace クラス」を参照してください、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]クラス ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-112">For more information about the **Trace** object, see "Trace Class" in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbcb1-113">ここに示すパターンは、場合と同じで、 **OrderHandler**インターフェイスが、クライアントとリモート オブジェクト間のメソッド呼び出しを指定します。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-113">The pattern here is the same as that in the **OrderHandler** in which an interface specifies the method calls between a client and a remoted object.</span></span> <span data-ttu-id="bbcb1-114">ただし、追加の間に次に、間接層、 **OpsClient**と**OpsHandler**です。</span><span class="sxs-lookup"><span data-stu-id="bbcb1-114">There is, however, an additional layer of indirection here between the **OpsClient** and the **OpsHandler**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbcb1-115">参照</span><span class="sxs-lookup"><span data-stu-id="bbcb1-115">See Also</span></span>  
 [<span data-ttu-id="bbcb1-116">Ops アダプタ</span><span class="sxs-lookup"><span data-stu-id="bbcb1-116">The Ops Adapter</span></span>](../core/the-ops-adapter.md)