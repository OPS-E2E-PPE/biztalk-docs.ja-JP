---
title: Windows Workflow Foundation での操作 |Microsoft ドキュメント
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
ms.openlocfilehash: 62cb1ba3cb82a21bb573145d00057112784c89a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265626"
---
# <a name="operations-in-windows-workflow-foundation"></a>Windows Workflow Foundation での操作
このセクションでは、BAM WF インターセプタによってサポートされているカスタム操作について説明します。  
  
## <a name="determining-where-operations-are-allowed"></a>操作を許可する場所の決定  
 BAM WF インターセプタから提供されているカスタム操作は、関連する Windows Workflow Foundation 追跡ポイントの種類ごとに分類することができます。  
  
-   アクティビティ  
  
-   ワークフロー  
  
-   ユーザー  
  
 BAM WF インターセプターでは、カテゴリを使用して、各追跡ポイントの種類を割り当てます**OnEvent**です。 この割り当てに表示される操作の種類に基づく、 **OnEvent**フィルターおよびデータの抽出、および操作セクションです。 たとえば場合、 **OnEvent**が含まれています、**更新**を使用する要素、 **GetUserData**は、アクティビティとワークフローのイベントが、ユーザー追跡ポイントの種類この操作をサポートしません。 追跡ポイントの詳細についてを参照してください System.Workflow.Runtime.Tracking [http://go.microsoft.com/fwlink/?LinkId=80242](http://go.microsoft.com/fwlink/?LinkId=80242)です。  
  
> [!NOTE]
>  ワークフロー追跡ポイントは、ワークフローからデータを抽出できません。  
  
 操作は、フィルタ式内とフィルタ式間の両方、および `OnEvent` 要素内のデータ抽出セクションと操作セクションでの互換性のあるものであることが必要です。 次の表に、各追跡ポイントの種類のフィルタ式に使用できる操作を示します。  
  
|フィルタ式の操作|アクティビティ追跡ポイントに対して有効|ワークフロー追跡ポイントに対して有効|ユーザー追跡ポイントに対して有効|  
|---------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|[等しい]|はい|可|はい|  
|And|はい|可|はい|  
|連結|不可|いいえ|不可|  
|定数|はい|可|はい|  
|GetActivityEvent|はい|いいえ|不可|  
|GetActivityName|はい|いいえ|はい|  
|GetActivityProperty|はい|いいえ|はい|  
|GetActivityType|はい|いいえ|はい|  
|GetContextProperty|不可|いいえ|不可|  
|GetUserData|不可|いいえ|不可|  
|GetUserDataType|不可|いいえ|はい|  
|GetUserKey|不可|いいえ|はい|  
|GetWorkflowEvent|不可|可|不可|  
|GetWorkflowProperty|不可|いいえ|不可|  
  
 互換性のない操作を組み合わせると、インターセプタ構成ファイルを展開するときにエラーが発生します。 たとえば、両方を使用する場合、`GetActivityEvent`と`GetWorkflowEvent`フィルター内または、フィルターおよびデータの抽出、または操作イベント (と同様に**CorrelationID**)、エラーが表示されます。  
  
 次の表に、データ抽出、または操作イベントの各アクティビティの種類でサポートされる操作についての概要を示します。  
  
|データ抽出、または操作|アクティビティ追跡ポイントに対して有効|ワークフロー追跡ポイントに対して有効|ユーザー追跡ポイントに対して有効|  
|-----------------------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|[等しい]|はい|可|はい|  
|And|はい|可|はい|  
|連結|はい|可|はい|  
|定数|はい|可|はい|  
|GetActivityEvent|はい|いいえ|不可|  
|GetActivityName|はい|いいえ|はい|  
|GetActivityProperty|はい|いいえ|はい|  
|GetActivityType|はい|いいえ|はい|  
|GetContextProperty|はい|可|はい|  
|GetUserData|不可|いいえ|はい|  
|GetUserDataType|不可|いいえ|はい|  
|GetUserKey|不可|いいえ|はい|  
|GetWorkflowEvent|不可|可|不可|  
|GetWorkflowProperty|はい|いいえ|はい|  
  
> [!NOTE]
>  1 つの間の一対一のマッピングがある**OnEvent**と単一の追跡ポイントです。  
  
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
 [BAM WF インターセプタ](../core/bam-wf-interceptor.md)