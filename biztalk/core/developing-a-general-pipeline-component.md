---
title: 全般パイプライン コンポーネントの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63f5d8d1-30fb-4a1e-b4bd-2be07b618b20
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7debc394b29676b15f330a8b5c22fbfe4656d0a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351542"
---
# <a name="developing-a-general-pipeline-component"></a><span data-ttu-id="9df31-102">全般パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="9df31-102">Developing a General Pipeline Component</span></span>

## <a name="interfaces"></a><span data-ttu-id="9df31-103">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9df31-103">Interfaces</span></span>
<span data-ttu-id="9df31-104">全般パイプライン コンポーネントは、次のインターフェイスを実装する .NET または COM コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9df31-104">A general pipeline component is a .NET or COM component that implements the following interfaces:</span></span>  
  
- <span data-ttu-id="9df31-105">IBaseComponent インターフェイス (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9df31-105">IBaseComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- <span data-ttu-id="9df31-106">IComponent インターフェイス (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9df31-106">IComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- <span data-ttu-id="9df31-107">IComponentUI インターフェイス (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9df31-107">IComponentUI Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- [<span data-ttu-id="9df31-108">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="9df31-108">IPersistPropertyBag</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
  <span data-ttu-id="9df31-109">全般パイプライン コンポーネントの 1 つのメッセージを BizTalk メッセージング エンジンから取得、処理し、しを返します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジン。</span><span class="sxs-lookup"><span data-stu-id="9df31-109">A general pipeline component gets one message from the BizTalk Messaging Engine, processes it, and returns it to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine.</span></span> <span data-ttu-id="9df31-110">メッセージをサーバーに返されないように全般コンポーネントを実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="9df31-110">General components can also be implemented so that they do not return messages to the server.</span></span> <span data-ttu-id="9df31-111">このようなコンポーネントでは、コンポーネントはメッセージを受信しますが、結果メッセージは生成されませんのでを破棄するコンポーネントと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9df31-111">Such components are called consuming components because the component receives messages but does not produce any result messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9df31-112">カスタム パイプライン コンポーネントは、出力メッセージ用に、入力メッセージからその他のパーツをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9df31-112">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="9df31-113">これはさらに、パイプラインで処理するためを保持します。</span><span class="sxs-lookup"><span data-stu-id="9df31-113">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="more-pipeline-resources"></a><span data-ttu-id="9df31-114">パイプラインの他のリソース</span><span class="sxs-lookup"><span data-stu-id="9df31-114">More pipeline resources</span></span>
 <span data-ttu-id="9df31-115">[アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9df31-115">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="9df31-116">[逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9df31-116">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="9df31-117">[プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9df31-117">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="9df31-118">[パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="9df31-118">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="9df31-119">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="9df31-119">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="9df31-120">[パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="9df31-120">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="9df31-121">CustomComponent (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9df31-121">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)