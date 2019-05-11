---
title: GetActivityProperty |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2321f1ec-d98d-478f-bb1d-a11a98e60fa5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca7eef66216eb8a3a2aae79d34fa7619ef96ef3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345095"
---
# <a name="getactivityproperty"></a>GetActivityProperty
追跡イベントに関連するアクティビティから抽出されたプロパティをスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetActivityProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>パラメーター  
 プロパティの名前です。  
  
## <a name="return-value"></a>戻り値  
 プロパティの値を格納している文字列。  
  
## <a name="remarks"></a>コメント  
 取得するプロパティ名を修飾するために、ドット付き表記を使用することができます。 これにより、プロパティを通じて公開される他のオブジェクト内のオブジェクトにアクセスできます。 たとえば、注文書の Address インスタンスの City プロパティにアクセスするには、"purchaseOrder.Address.City" を使用します。  
  
 プロパティ名は、最初は大文字と小文字が区別され、その後は大文字と小文字が区別されません。 これは、WF アプリケーションで、大文字と小文字の区別のみが異なる複数のアクティビティ プロパティを使用する場合に重要です。 たとえば、ワークフロー アプリケーションで "myWorkflow" プロパティと "MyWorkflow" プロパティを定義している場合に "MyWorkflow" を検索すると、大文字と小文字を区別する照合において "MyWorkflow" プロパティが検索されます。 "MYWORKFLOW" と指定すると、大文字と小文字を区別する照合に失敗してから、大文字と小文字を区別しない照合において "myWorkflow" プロパティが検索されます。  
  
 たとえば、大文字と小文字のみが異なる "myProperty" と "MyProperty" の 2 つのアクティビティ プロパティを使用する場合が該当します。  
  
> [!NOTE]
>  NULL プロパティ値を使用すると、ワークフロー インスタンスに NullReferenceException がスローされます。  
  
## <a name="example"></a>例  
 次の例では、更新された式でアクティビティ プロパティ "MyProperty" を保持するために、`GetActivityProperty` が使用されています。  
  
```  
<ic:Update DataItemName="TextData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetActivityProperty">  
      <wf:Argument>MyProperty</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```