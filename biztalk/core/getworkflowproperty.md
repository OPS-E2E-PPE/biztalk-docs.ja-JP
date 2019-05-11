---
title: GetWorkflowProperty |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9d3029e-3267-46bc-ba2e-1c6fa1f2e931
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53e31ea557508164bd5e434558ebdf6bb0689a7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344906"
---
# <a name="getworkflowproperty"></a>GetWorkflowProperty
スタックにワークフローのルート アクティビティから抽出されたプロパティをプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>パラメーター  
 プロパティの名前です。  
  
## <a name="pushed-value"></a>プッシュされた値  
 プロパティの値を格納している文字列。  
  
## <a name="remarks"></a>コメント  
 この操作で、更新プログラムのみです。  
  
 取得するプロパティ名を修飾するために、ドット付き表記を使用することができます。 これにより、プロパティを通じて公開される他のオブジェクト内のオブジェクトにアクセスできます。 たとえば、注文書の Address インスタンスの City プロパティにアクセスするには、"purchaseOrder.Address.City" を使用します。  
  
 プロパティ名は、最初は大文字と小文字が区別され、その後は大文字と小文字が区別されません。 これは、WF アプリケーションで、大文字と小文字の区別のみが異なる複数のアクティビティ プロパティを使用する場合に重要です。 たとえば、ワークフロー アプリケーションで "myWorkflow" プロパティと "MyWorkflow" プロパティを定義している場合に "MyWorkflow" を検索すると、大文字と小文字を区別する照合において "MyWorkflow" プロパティが検索されます。 "MYWORKFLOW"を指定すると、大文字と小文字の試行が失敗した後に"myWorkflow"で大文字と小文字が一致してしまいます。  
  
> [!NOTE]
>  NULL プロパティ値を使用すると、ワークフロー インスタンスに NullReferenceException がスローされます。  
  
## <a name="example"></a>例  
 Update 式を使用すると、注文書からワークフロー プロパティ"City"を使用して永続化では、次の例では、`GetWorkflowProperty`します。  
  
```  
<ic:Update DataItemName="City" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>po.Info.City</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```