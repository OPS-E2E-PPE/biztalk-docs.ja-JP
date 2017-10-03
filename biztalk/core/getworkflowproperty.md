---
title: "GetWorkflowProperty |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9d3029e-3267-46bc-ba2e-1c6fa1f2e931
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505fc41ce544cdf16e3826116514ba1991ba012e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="getworkflowproperty"></a>GetWorkflowProperty
ワークフローのルート アクティビティから抽出されたプロパティをスタックにプッシュします。  
  
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
  
## <a name="remarks"></a>解説  
 この操作は、更新でのみ有効です。  
  
 取得するプロパティ名を修飾するために、ドット付き表記を使用することができます。 これにより、プロパティを通じて公開される他のオブジェクト内のオブジェクトにアクセスできます。 たとえば、注文書の Address インスタンスの City プロパティにアクセスするには、"purchaseOrder.Address.City" を使用します。  
  
 プロパティ名は、最初は大文字と小文字が区別され、その後は大文字と小文字が区別されません。 これは、WF アプリケーションで、大文字と小文字の区別のみが異なる複数のアクティビティ プロパティを使用する場合に重要です。 たとえば、ワークフロー アプリケーションで "myWorkflow" プロパティと "MyWorkflow" プロパティを定義している場合に "MyWorkflow" を検索すると、大文字と小文字を区別する照合において "MyWorkflow" プロパティが検索されます。 "MYWORKFLOW"を指定する場合は一致において"myWorkflow"大文字と小文字を大文字と小文字の試行が失敗した後にします。  
  
> [!NOTE]
>  NULL プロパティ値を使用すると、ワークフロー インスタンスに NullReferenceException がスローされます。  
  
## <a name="example"></a>例  
 次の例では、更新された式で注文書のワークフロー プロパティ "City" を保持するために、`GetWorkflowProperty` が使用されています。  
  
```  
<ic:Update DataItemName="City" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>po.Info.City</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```