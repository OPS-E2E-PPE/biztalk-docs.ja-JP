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
# <a name="how-to-deploy-policies"></a>ポリシーを展開する方法
使用してプログラムでポリシーを展開することができます、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)クラス、 **Microsoft.RuleEngine.RuleEngineExtensions**名前空間。 次のサンプル コードを使用する方法を示します、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)という名前のポリシーを展開するにはクラス**LoanProcessing**:  
  
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
>  オーバー ロードされたコンス トラクター、 [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)クラスは、パラメーターとして、ルール ストア データベースの名前を受け取ります。 BizTalk Server 環境は構成されていないデータベースにポリシーを展開することができますを使用します。  
  
## <a name="using-the-getdeploymentdriver-method"></a>GetDeploymentDriver メソッドの使用  
 データベースにポリシーを展開する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用する環境が構成されている、作成する必要はありません、 **RuleSetDeploymentDriver**コード内のオブジェクト。 代わりに、作成するルール エンジンを要求することができます、 **RuleSetDeploymentDriver**オブジェクトを呼び出すことによって、 **GetDeploymentDriver**のメソッド、**構成**クラス、 **System.RuleEngine**名前空間。 次のサンプル コードが呼び出す方法を示します、 **GetDeploymentDriver**メソッド。  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 **GetDeploymentDriver**メソッドの値を取得、 **\software\microsoft\businessrules\3.0**と**DeploymentDriverClass**下のレジストリ キー **hkey _LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**のインスタンスを作成および**DeploymentDriverClass**します。 次の表では、これらの 2 つのレジストリ キーの既定値を示します。  
  
|レジストリ キー|値|  
|------------------|-----------|  
|DeploymentDriverAssembly|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
  
 **RuleSetDeploymentDriver**クラスが実装する、 **IRuleSetDeploymentDriver**インターフェイス。 実装するクラスを作成して、独自のポリシー展開ドライバーを開発することができます、 **IRuleSetDeploymentDriver**インターフェイスおよびとして上記のレジストリ キーの値で説明した変更が適切な。