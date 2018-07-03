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
ms.openlocfilehash: 057154a2e64541b00c704be7078ef27ba596de20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007603"
---
# <a name="operations-in-windows-workflow-foundation"></a>Windows Workflow Foundation での操作
このセクションでは、BAM WF インターセプタによってサポートされているカスタム操作について説明します。  
  
## <a name="determining-where-operations-are-allowed"></a>操作を許可する場所の決定  
 BAM WF インターセプタから提供されているカスタム操作は、関連する Windows Workflow Foundation 追跡ポイントの種類ごとに分類することができます。  
  
- アクティビティ  
  
- ワークフロー  
  
- ユーザー  
  
  BAM WF インターセプタは、カテゴリを使用して、各追跡ポイントの種類を割り当てるを**OnEvent**します。 この割り当てに表示される操作の種類に基づく、 **OnEvent**フィルターとデータの抽出、および操作セクション。 たとえば場合、 **OnEvent**が含まれています、 **Update**を使用する要素、 **GetUserData**アクティビティとワークフロー イベントを行うため、ユーザー追跡ポイントの種類は、その操作、この操作をサポートします。 追跡ポイントの詳細については、System.Workflow.Runtime.Tracking を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=80242](http://go.microsoft.com/fwlink/?LinkId=80242)します。  
  
> [!NOTE]
>  ワークフロー追跡ポイントは、ワークフローからデータを抽出できません。  
  
 操作は、フィルタ式内とフィルタ式間の両方、および `OnEvent` 要素内のデータ抽出セクションと操作セクションでの互換性のあるものであることが必要です。 次の表に、各追跡ポイントの種類のフィルタ式に使用できる操作を示します。  
  
|フィルタ式の操作|アクティビティ追跡ポイントに対して有効|ワークフロー追跡ポイントに対して有効|ユーザー追跡ポイントに対して有効|  
|---------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|[等しい]|はい|はい|はい|  
|And|はい|はい|はい|  
|連結|いいえ|いいえ|いいえ|  
|定数|はい|はい|はい|  
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
  
 互換性のない操作を組み合わせると、インターセプタ構成ファイルを展開するときにエラーが発生します。 両方を使用する場合など、`GetActivityEvent`と`GetWorkflowEvent`フィルター、内またはフィルター処理およびデータ抽出、または操作イベント (など**CorrelationID**)、エラーが表示されます。  
  
 次の表に、データ抽出、または操作イベントの各アクティビティの種類でサポートされる操作についての概要を示します。  
  
|データ抽出、または操作|アクティビティ追跡ポイントに対して有効|ワークフロー追跡ポイントに対して有効|ユーザー追跡ポイントに対して有効|  
|-----------------------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|[等しい]|はい|はい|はい|  
|And|はい|はい|はい|  
|連結|はい|はい|はい|  
|定数|はい|はい|はい|  
|GetActivityEvent|はい|いいえ|いいえ|  
|GetActivityName|はい|いいえ|はい|  
|GetActivityProperty|はい|いいえ|はい|  
|GetActivityType|はい|いいえ|はい|  
|GetContextProperty|はい|はい|はい|  
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