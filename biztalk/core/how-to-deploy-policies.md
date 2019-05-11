---
title: ポリシーを展開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c4ab85a-5a6a-4153-90dc-52e099c0a62c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d318437c6ddb62b52599ce6da51022775ad1fcd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338629"
---
# <a name="how-to-deploy-policies"></a><span data-ttu-id="69f95-102">ポリシーを展開する方法</span><span class="sxs-lookup"><span data-stu-id="69f95-102">How to Deploy Policies</span></span>
<span data-ttu-id="69f95-103">使用してプログラムでポリシーを展開することができます、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)クラス、 **Microsoft.RuleEngine.RuleEngineExtensions**名前空間。</span><span class="sxs-lookup"><span data-stu-id="69f95-103">You can deploy policies programmatically by using the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class in the **Microsoft.RuleEngine.RuleEngineExtensions** namespace.</span></span> <span data-ttu-id="69f95-104">次のサンプル コードを使用する方法を示します、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)という名前のポリシーを展開するにはクラス**LoanProcessing**:</span><span class="sxs-lookup"><span data-stu-id="69f95-104">The following sample code demonstrates how to use the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class to deploy a policy named **LoanProcessing**:</span></span>  
  
```  
string policyName = “LoanProcessing”;  
int majorRev = Convert.ToInt16(args[1]);  
int minorRev = Convert.ToInt16(args[2]);  
RuleSetInfo rsi = new RuleSetInfo(policyName,majorRev,minorRev);  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
dd.Deploy(rsi);  
```  
  
> [!NOTE]
>  <span data-ttu-id="69f95-105">オーバー ロードされたコンス トラクター、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)クラスは、パラメーターとして、ルール ストア データベースの名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="69f95-105">The overloaded constructors of the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class take the names of the rule store database as a parameter.</span></span> <span data-ttu-id="69f95-106">BizTalk Server 環境は構成されていないデータベースにポリシーを展開することができますを使用します。</span><span class="sxs-lookup"><span data-stu-id="69f95-106">This allows you to deploy policies to a database that your BizTalk Server environment is not configured to use.</span></span>  
  
## <a name="using-the-getdeploymentdriver-method"></a><span data-ttu-id="69f95-107">GetDeploymentDriver メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="69f95-107">Using the GetDeploymentDriver Method</span></span>  
 <span data-ttu-id="69f95-108">データベースにポリシーを展開する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用する環境が構成されている、作成する必要はありません、 **RuleSetDeploymentDriver**コード内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="69f95-108">If you are deploying policies to the database that your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is configured to use, you do not have to create the **RuleSetDeploymentDriver** object in the code.</span></span> <span data-ttu-id="69f95-109">代わりに、作成するルール エンジンを要求することができます、 **RuleSetDeploymentDriver**オブジェクトを呼び出すことによって、 **GetDeploymentDriver**のメソッド、**構成**クラス、 **System.RuleEngine**名前空間。</span><span class="sxs-lookup"><span data-stu-id="69f95-109">Instead, you can request the rule engine to create a **RuleSetDeploymentDriver** object for you by invoking the **GetDeploymentDriver** method of the **Configuration** class in the **System.RuleEngine** namespace.</span></span> <span data-ttu-id="69f95-110">次のサンプル コードが呼び出す方法を示します、 **GetDeploymentDriver**メソッド。</span><span class="sxs-lookup"><span data-stu-id="69f95-110">The following sample code demonstrates how to invoke the **GetDeploymentDriver** method:</span></span>  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 <span data-ttu-id="69f95-111">**GetDeploymentDriver**メソッドの値を取得、 **\software\microsoft\businessrules\3.0**と**DeploymentDriverClass**下のレジストリ キー **hkey _LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**のインスタンスを作成および**DeploymentDriverClass**します。</span><span class="sxs-lookup"><span data-stu-id="69f95-111">The **GetDeploymentDriver** method retrieves the values of the **DeploymentDriverAssembly** and **DeploymentDriverClass** registry keys under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, and creates an instance of **DeploymentDriverClass**.</span></span> <span data-ttu-id="69f95-112">次の表では、これらの 2 つのレジストリ キーの既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="69f95-112">The following table shows the default values of these two registry keys.</span></span>  
  
|<span data-ttu-id="69f95-113">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="69f95-113">Registry key</span></span>|<span data-ttu-id="69f95-114">値</span><span class="sxs-lookup"><span data-stu-id="69f95-114">Value</span></span>|  
|------------------|-----------|  
|<span data-ttu-id="69f95-115">DeploymentDriverAssembly</span><span class="sxs-lookup"><span data-stu-id="69f95-115">DeploymentDriverAssembly</span></span>|<span data-ttu-id="69f95-116">Microsoft.BizTalk.RuleEngineExtensions</span><span class="sxs-lookup"><span data-stu-id="69f95-116">Microsoft.BizTalk.RuleEngineExtensions</span></span>|  
|<span data-ttu-id="69f95-117">DeploymentDriverClass</span><span class="sxs-lookup"><span data-stu-id="69f95-117">DeploymentDriverClass</span></span>|<span data-ttu-id="69f95-118">Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver</span><span class="sxs-lookup"><span data-stu-id="69f95-118">Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver</span></span>|  
  
 <span data-ttu-id="69f95-119">**RuleSetDeploymentDriver**クラスが実装する、 **IRuleSetDeploymentDriver**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="69f95-119">The **RuleSetDeploymentDriver** class implements the **IRuleSetDeploymentDriver** interface.</span></span> <span data-ttu-id="69f95-120">実装するクラスを作成して、独自のポリシー展開ドライバーを開発することができます、 **IRuleSetDeploymentDriver**インターフェイスおよびとして上記のレジストリ キーの値で説明した変更が適切な。</span><span class="sxs-lookup"><span data-stu-id="69f95-120">You can develop your own policy deployment driver by creating a class that implements the **IRuleSetDeploymentDriver** interface and change the values for the registry keys described above as appropriate.</span></span>