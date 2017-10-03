---
title: "ポリシーを展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c4ab85a-5a6a-4153-90dc-52e099c0a62c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c3b07b0a8cebdd3322b49732ef4f32c04cbfede
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-policies"></a>ポリシーを展開する方法
使用してポリシーをプログラムで配置することができます、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)クラス内で、 **Microsoft.RuleEngine.RuleEngineExtensions**名前空間。 次のサンプル コードを使用する方法を示しています、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)という名前のポリシーを展開するクラス**LoanProcessing**:  
  
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
>  オーバー ロードされたコンス トラクター、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)クラスは、パラメーターとして、ルール ストア データベースの名前を受け取ります。 これにより、BizTalk Server 環境で使用するように構成されていないデータベースにポリシーを展開することができます。  
  
## <a name="using-the-getdeploymentdriver-method"></a>GetDeploymentDriver メソッドの使用  
 データベースにポリシーを展開する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用する環境が構成されている、作成する必要はありません、 **RuleSetDeploymentDriver**コード内のオブジェクト。 作成するルール エンジンを要求する代わりに、 **RuleSetDeploymentDriver**オブジェクトを呼び出すことによって、 **GetDeploymentDriver**のメソッド、**構成**クラスの**System.RuleEngine**名前空間。 次のサンプル コードを呼び出す方法を示しています、 **GetDeploymentDriver**メソッド。  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 **GetDeploymentDriver**メソッドの値を取得、 **\software\microsoft\businessrules\3.0**と**DeploymentDriverClass**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**のインスタンスを作成し、 **DeploymentDriverClass**です。 次の表に、これら 2 つのレジストリ キーの既定値を示します。  
  
|レジストリ キー|値|  
|------------------|-----------|  
|DeploymentDriverAssembly|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
  
 **RuleSetDeploymentDriver**クラスが実装する、 **IRuleSetDeploymentDriver**インターフェイスです。 実装するクラスを作成することで、独自のポリシー展開ドライバーを開発することができます、 **IRuleSetDeploymentDriver**インターフェイスと変更として上のレジストリ キーの値で説明した適切な。