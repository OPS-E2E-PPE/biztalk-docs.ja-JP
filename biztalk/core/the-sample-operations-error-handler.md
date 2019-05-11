---
title: サンプル操作エラー ハンドラ |Microsoft Docs
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
ms.openlocfilehash: 3ad378180fbf6b29ce69c21a5546243d8891fd81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379931"
---
# <a name="the-sample-operations-error-handler"></a><span data-ttu-id="68953-102">サンプル操作エラー ハンドラ</span><span class="sxs-lookup"><span data-stu-id="68953-102">The Sample Operations Error Handler</span></span>
<span data-ttu-id="68953-103">サンプル操作エラー ハンドラでは、3 つの主要なアセンブリがあります。**OperationsClient**、 **OperationsHandler**、および**OperationsServer**します。</span><span class="sxs-lookup"><span data-stu-id="68953-103">The sample operations error handler has three major assemblies: **OperationsClient**, **OperationsHandler**, and **OperationsServer**.</span></span>  
  
 <span data-ttu-id="68953-104">ソリューションを使用するアダプターの構成、 **OpsClient**オブジェクト、 **OperationsClient**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="68953-104">The solution configures the adapter to use the **OpsClient** object in the **OperationsClient** assembly.</span></span> <span data-ttu-id="68953-105">想定されるよう、 **OpsClient**オブジェクトの実装、 **IOpsAIC**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="68953-105">As you'd expect, the **OpsClient** object implements the **IOpsAIC** interface.</span></span>  
  
 <span data-ttu-id="68953-106">**OpsClient**オブジェクトで使用、 **IOperationsSystem**インターフェイスを呼び出す、 **OpsHandler**オブジェクト、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]リモート処理機能です。</span><span class="sxs-lookup"><span data-stu-id="68953-106">The **OpsClient** object uses the **IOperationsSystem** interface to call the **OpsHandler** object through the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] remoting feature.</span></span> <span data-ttu-id="68953-107">**IOperationsSystem**インターフェイスが次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="68953-107">The **IOperationsSystem** interface appears as follows:</span></span>  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 <span data-ttu-id="68953-108">**OperationsServer**、コンソール アプリケーションの要求をリッスン、 **OpsHandler**オブジェクトし、サーバーの役割を果たします、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]リモート処理機能です。</span><span class="sxs-lookup"><span data-stu-id="68953-108">The **OperationsServer**, a console application, listens for requests for the **OpsHandler** object and acts as the server for the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] remoting feature.</span></span> <span data-ttu-id="68953-109">呼び出す、 **Execute**のメソッド、 **OpsClient**オブジェクトが順番に呼び出す、 **Post**のメソッド、 **OpsHandler**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="68953-109">Calling the **Execute** method of the **OpsClient** object in turn invokes the **Post** method of the **OpsHandler** object.</span></span>  
  
 <span data-ttu-id="68953-110">**OpsHandler**メソッドの応答を使用して、引数文字列を記述することで、**トレース**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="68953-110">The **OpsHandler** methods respond by writing out their argument strings using the **Trace** object.</span></span> <span data-ttu-id="68953-111">これは、コンソールにエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="68953-111">This posts the errors to the console.</span></span> <span data-ttu-id="68953-112">詳細については、**トレース**オブジェクト「Trace クラス」を参照してください、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]クラス ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="68953-112">For more information about the **Trace** object, see "Trace Class" in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68953-113">ここに示すパターンは、のと同じ、 **OrderHandler**インターフェイスが、クライアントとリモート オブジェクト間のメソッド呼び出しを指定します。</span><span class="sxs-lookup"><span data-stu-id="68953-113">The pattern here is the same as that in the **OrderHandler** in which an interface specifies the method calls between a client and a remoted object.</span></span> <span data-ttu-id="68953-114">ただし、間にここで間接参照の追加レイヤー、 **OpsClient**と**OpsHandler**します。</span><span class="sxs-lookup"><span data-stu-id="68953-114">There is, however, an additional layer of indirection here between the **OpsClient** and the **OpsHandler**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68953-115">参照</span><span class="sxs-lookup"><span data-stu-id="68953-115">See Also</span></span>  
 [<span data-ttu-id="68953-116">Ops アダプター</span><span class="sxs-lookup"><span data-stu-id="68953-116">The Ops Adapter</span></span>](../core/the-ops-adapter.md)