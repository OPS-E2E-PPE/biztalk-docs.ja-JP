---
title: "全般パイプライン コンポーネントの開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63f5d8d1-30fb-4a1e-b4bd-2be07b618b20
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44b85992eb0691b7f27ec1a52812d986429d9e31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="developing-a-general-pipeline-component"></a><span data-ttu-id="b8225-102">全般パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="b8225-102">Developing a General Pipeline Component</span></span>

## <a name="interfaces"></a><span data-ttu-id="b8225-103">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8225-103">Interfaces</span></span>
<span data-ttu-id="b8225-104">全般パイプライン コンポーネントは、次のインターフェイスを実装する .NET コンポーネントまたは COM コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="b8225-104">A general pipeline component is a .NET or COM component that implements the following interfaces:</span></span>  
  
-   <span data-ttu-id="b8225-105">IBaseComponent インターフェイス (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b8225-105">IBaseComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   <span data-ttu-id="b8225-106">IComponent インターフェイス (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b8225-106">IComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   <span data-ttu-id="b8225-107">IComponentUI インターフェイス (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b8225-107">IComponentUI Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="b8225-108">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="b8225-108">IPersistPropertyBag</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
 <span data-ttu-id="b8225-109">全般パイプライン コンポーネントは、BizTalk メッセージング エンジンからメッセージを 1 つ取得して処理し、そのメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンに返します。</span><span class="sxs-lookup"><span data-stu-id="b8225-109">A general pipeline component gets one message from the BizTalk Messaging Engine, processes it, and returns it to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine.</span></span> <span data-ttu-id="b8225-110">メッセージがサーバーに返されないように全般コンポーネントを実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8225-110">General components can also be implemented so that they do not return messages to the server.</span></span> <span data-ttu-id="b8225-111">このようなコンポーネントは、メッセージを受信しても結果メッセージをまったく生成しないので、"メッセージを破棄するコンポーネント" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b8225-111">Such components are called consuming components because the component receives messages but does not produce any result messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8225-112">カスタム パイプライン コンポーネントでは入力メッセージの追加部分を出力メッセージにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8225-112">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="b8225-113">これにより、パイプラインでの後続の処理のために追加部分が保持されます。</span><span class="sxs-lookup"><span data-stu-id="b8225-113">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="more-pipeline-resources"></a><span data-ttu-id="b8225-114">パイプラインの他のリソース</span><span class="sxs-lookup"><span data-stu-id="b8225-114">More pipeline resources</span></span>
 <span data-ttu-id="b8225-115">[アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="b8225-115">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="b8225-116">[逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="b8225-116">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="b8225-117">[プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="b8225-117">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="b8225-118">[パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b8225-118">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="b8225-119">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b8225-119">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="b8225-120">[パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b8225-120">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="b8225-121">CustomComponent (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="b8225-121">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)