---
title: Windows SharePoint Services アダプターに関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c20eda7-643d-484c-bf5d-59ff69604cea
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ed4f0961bc80a3fe858caaca1d4aa51644912be
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970704"
---
# <a name="known-issues-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="18eb2-102">Windows SharePoint Services アダプタに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="18eb2-102">Known Issues with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="18eb2-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="18eb2-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="18eb2-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="18eb2-104">Known Issues</span></span>  
  
#### <a name="wss-adapter-fails-to-start-a-workflow-attached-to-a-doc-librarysharepoint-list"></a><span data-ttu-id="18eb2-105">WSS アダプターがドキュメント ライブラリ/SharePoint リストに添付されているワークフローを開始できない</span><span class="sxs-lookup"><span data-stu-id="18eb2-105">WSS Adapter Fails to Start a Workflow attached to a Doc Library/Sharepoint List</span></span>  
 <span data-ttu-id="18eb2-106">WSS アダプターを使用して BizTalk からドキュメント ライブラリ/SharePoint リストにドキュメントまたはリスト アイテムを発行するときに、そのリストに添付されているワークフローを開始できません。</span><span class="sxs-lookup"><span data-stu-id="18eb2-106">When using the WSS Adapter from BizTalk to submit either a document or list item to a Doc Library/Sharepoint List, it fails to start the workflow attached to that List.</span></span> <span data-ttu-id="18eb2-107">この問題を回避するには、以下の XML コードを \Program Files\Microsoft BizTalk Server 20xx\Business Activity Services\BTSharePointV3AdapterWS\web.config ファイルにコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="18eb2-107">The workaround is to copy the XML code below into the \Program Files\Microsoft BizTalk Server 20xx\Business Activity Services\BTSharePointV3AdapterWS\web.config file.</span></span>  <span data-ttu-id="18eb2-108">以下の XML 内のコードを挿入する必要があります、\<構成\>要素。</span><span class="sxs-lookup"><span data-stu-id="18eb2-108">The below XML code must be inserted inside of the \<configuration\> element.</span></span>  
  
```  
<configSections>  
    <sectionGroup name="System.Workflow.ComponentModel.WorkflowCompiler" type="System.Workflow.ComponentModel.Compiler.WorkflowCompilerConfigurationSectionGroup, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">  
      <section name="authorizedTypes" type="System.Workflow.ComponentModel.Compiler.AuthorizedTypesSectionHandler, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </sectionGroup>  
  </configSections>  
  <System.Workflow.ComponentModel.WorkflowCompiler>  
    <authorizedTypes>  
      <authorizedType Assembly="System.Workflow.Activities, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Namespace="System.Workflow.*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Namespace="System.Workflow.*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="System.Workflow.Runtime, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Namespace="System.Workflow.*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="Microsoft.SharePoint, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" Namespace="Microsoft.SharePoint.Workflow" TypeName="SPWorkflowActivationProperties" Authorized="True" />  
      <authorizedType Assembly="Microsoft.SharePoint, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" Namespace="Microsoft.SharePoint.Workflow" TypeName="SPWorkflowTaskProperties" Authorized="True" />  
      <authorizedType Assembly="Microsoft.SharePoint, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" Namespace="Microsoft.SharePoint.Workflow" TypeName="SPWorkflowHistoryEventType" Authorized="True" />  
      <authorizedType Assembly="Microsoft.SharePoint.WorkflowActions, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" Namespace="Microsoft.SharePoint.WorkflowActions" TypeName="*" Authorized="True" />  
    </authorizedTypes>  
  </System.Workflow.ComponentModel.WorkflowCompiler>  
  
```