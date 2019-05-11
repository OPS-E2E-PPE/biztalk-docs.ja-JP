---
title: アダプター インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7398aeb-7c1c-400e-a552-d0ab39e55a0b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdb6f3e26d8862fd538f0279ecbb4c5c9b33af8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361404"
---
# <a name="adapter-interfaces"></a><span data-ttu-id="8f0d9-102">アダプター インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f0d9-102">Adapter Interfaces</span></span>
<span data-ttu-id="8f0d9-103">カスタム アダプターを実装する必要があります、3 つのインターフェイスと省略可能な 2 つのインターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-103">There are three interfaces that custom adapters must implement, and two interfaces that are optional.</span></span>  
  
## <a name="mandatory-interfaces"></a><span data-ttu-id="8f0d9-104">必須のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f0d9-104">Mandatory interfaces</span></span>  
 <span data-ttu-id="8f0d9-105">すべてのアダプターでは、次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-105">All adapters must implement the following interfaces.</span></span>  
  
### <a name="ibasecomponent"></a><span data-ttu-id="8f0d9-106">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="8f0d9-106">IBaseComponent</span></span>  
 <span data-ttu-id="8f0d9-107">このインターフェイスの詳細、**名前**、**バージョン**、および**説明**アダプターの。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-107">This interface details the **Name**, **Version**, and **Description** of the adapter.</span></span>  
  
### <a name="ibttransport"></a><span data-ttu-id="8f0d9-108">IBTTransport</span><span class="sxs-lookup"><span data-stu-id="8f0d9-108">IBTTransport</span></span>  
 <span data-ttu-id="8f0d9-109">このインターフェイスの詳細、**トランスポートの種類**と**ClassID**のアダプター。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-109">This interface details the **Transport Type** and **ClassID** of the adapter.</span></span>  
  
### <a name="ibtbatchcallback"></a><span data-ttu-id="8f0d9-110">IBTBatchCallback</span><span class="sxs-lookup"><span data-stu-id="8f0d9-110">IBTBatchCallback</span></span>  
 <span data-ttu-id="8f0d9-111">このインターフェイスは、アダプター情報を受信状態やエラー メッセージのバッチのメッセージング エンジンに送信されるコールバック インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-111">This interface is a callback interface through which the adapter receives status and error information for a batch of messages it submits to the Messaging Engine.</span></span>  
  
## <a name="optional-interfaces"></a><span data-ttu-id="8f0d9-112">省略可能なインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f0d9-112">Optional interfaces</span></span>  
 <span data-ttu-id="8f0d9-113">アダプターは、必要に応じて、次のインターフェイスを実装していません。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-113">Adapters may or may not implement the following interfaces, depending on their needs.</span></span>  
  
### <a name="ipersistpropertybag"></a><span data-ttu-id="8f0d9-114">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="8f0d9-114">IPersistPropertyBag</span></span>  
 <span data-ttu-id="8f0d9-115">これは、どのハンドラーを通じて構成は、アダプターに配信構成インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-115">This is a configuration interface through which handler configuration is delivered to the adapter.</span></span> <span data-ttu-id="8f0d9-116">このインターフェイスは、ハンドラーの構成情報を持つアダプターに対してのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-116">This interface is required only for adapters that have handler configuration information.</span></span>  
  
### <a name="ibttransportcontrol"></a><span data-ttu-id="8f0d9-117">IBTTransportControl</span><span class="sxs-lookup"><span data-stu-id="8f0d9-117">IBTTransportControl</span></span>  
 <span data-ttu-id="8f0d9-118">このインターフェイスは初期化し、アダプターの終了に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-118">This interface is used to initialize and terminate an adapter.</span></span> <span data-ttu-id="8f0d9-119">アダプターのトランスポート プロキシは、このインターフェイスを使用して渡されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-119">The adapter's transport proxy is passed to it through this interface.</span></span> <span data-ttu-id="8f0d9-120">このインターフェイスは、分離アダプターの必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-120">This interface is not required for isolated adapters.</span></span>