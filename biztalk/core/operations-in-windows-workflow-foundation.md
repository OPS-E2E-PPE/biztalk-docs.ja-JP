---
title: Windows Workflow Foundation での操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a048dfc0-26b2-4f20-9d2f-c52f1ab19ac3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b602bfee7c2f57453243fb56bccd63183a45f543
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263027"
---
# <a name="operations-in-windows-workflow-foundation"></a>Windows Workflow Foundation での操作
このセクションには、BAM WF インターセプタによってサポートされるカスタム操作が含まれています。  
  
## <a name="determining-where-operations-are-allowed"></a>操作が許可された場所を決定します。  
 BAM WF インターセプタによって提供されるカスタムの操作に関連付けられている Windows Workflow Foundation 追跡ポイントの種類で分類できます。  
  
- アクティビティ  
  
- ワークフロー  
  
- ユーザー  
  
  BAM WF インターセプタは、カテゴリを使用して、各追跡ポイントの種類を割り当てるを**OnEvent**します。 この割り当てに表示される操作の種類に基づく、 **OnEvent**フィルターとデータの抽出、および操作セクション。 たとえば場合、 **OnEvent**が含まれています、 **Update**を使用する要素、 **GetUserData**アクティビティとワークフロー イベントを行うため、ユーザー追跡ポイントの種類は、その操作、この操作をサポートします。 追跡ポイントの詳細については、System.Workflow.Runtime.Tracking を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=80242](http://go.microsoft.com/fwlink/?LinkId=80242)します。  
  
> [!NOTE]
>  ワークフロー追跡ポイントは、ワークフローからデータを抽出することはできません。  
  
 操作は、互換性のあるフィルター式内とフィルター式とデータの抽出、および操作セクション内の間の両方である必要があります、`OnEvent`要素。 次の表は、どのような操作は、各追跡ポイントの種類のフィルター式で使用できます。  
  
|フィルター式の操作|アクティビティ追跡ポイントに対して有効ですか。|ワークフロー追跡ポイントに対して有効ですか。|ユーザー追跡ポイントに対して有効ですか。|  
|---------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|[等しい]|はい|[はい]|はい|  
|And|はい|[はい]|はい|  
|連結|いいえ|いいえ|いいえ|  
|定数|はい|[はい]|はい|  
|GetActivityEvent|はい|いいえ|いいえ|  
|GetActivityName|はい|いいえ|はい|  
|GetActivityProperty|はい|いいえ|はい|  
|GetActivityType|はい|いいえ|はい|  
|GetContextProperty|いいえ|いいえ|いいえ|  
|GetUserData|いいえ|いいえ|いいえ|  
|GetUserDataType|いいえ|いいえ|はい|  
|GetUserKey|いいえ|いいえ|はい|  
|GetWorkflowEvent|いいえ|はい|いいえ|  
|GetWorkflowProperty|いいえ|いいえ|いいえ|  
  
 互換性のない操作が混在する場合、インターセプタ構成ファイルを配置するときにエラーを受け取ります。 両方を使用する場合など、`GetActivityEvent`と`GetWorkflowEvent`フィルター、内またはフィルター処理およびデータ抽出、または操作イベント (など**CorrelationID**)、エラーが表示されます。  
  
 次の表は、データの抽出、または操作の各アクティビティの種類をサポートする操作をまとめたものです。  
  
|データの抽出、または操作|アクティビティ追跡ポイントに対して有効ですか。|ワークフロー追跡ポイントに対して有効ですか。|ユーザー追跡ポイントに対して有効ですか。|  
|-----------------------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|[等しい]|はい|[はい]|はい|  
|And|はい|[はい]|はい|  
|連結|はい|[はい]|はい|  
|定数|はい|[はい]|はい|  
|GetActivityEvent|はい|いいえ|いいえ|  
|GetActivityName|はい|いいえ|はい|  
|GetActivityProperty|はい|いいえ|はい|  
|GetActivityType|はい|いいえ|はい|  
|GetContextProperty|はい|[はい]|はい|  
|GetUserData|いいえ|いいえ|はい|  
|GetUserDataType|いいえ|いいえ|はい|  
|GetUserKey|いいえ|いいえ|はい|  
|GetWorkflowEvent|いいえ|はい|いいえ|  
|GetWorkflowProperty|はい|いいえ|はい|  
  
> [!NOTE]
>  1 つの間の一対一のマッピングがある**OnEvent**と単一の追跡ポイント。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [GetActivityEvent](../core/getactivityevent.md)  
  
-   [GetActivityName](../core/getactivityname.md)  
  
-   [GetActivityProperty](../core/getactivityproperty.md)  
  
-   [GetActivityType](../core/getactivitytype.md)  
  
-   [GetContextProperty](../core/getcontextproperty2.md)  
  
-   [GetUserData](../core/getuserdata.md)  
  
-   [GetUserDataType](../core/getuserdatatype.md)  
  
-   [GetUserKey](../core/getuserkey.md)  
  
-   [GetWorkflowEvent](../core/getworkflowevent.md)  
  
-   [GetWorkflowProperty](../core/getworkflowproperty.md)  
  
## <a name="see-also"></a>参照  
 [BAM WF インターセプター](../core/bam-wf-interceptor.md)