---
title: アダプター インターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: 717adcf5d4a706a7cc072b42b224ab0f9f8cc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225490"
---
# <a name="adapter-interfaces"></a><span data-ttu-id="aa4e0-102">アダプター インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa4e0-102">Adapter Interfaces</span></span>
<span data-ttu-id="aa4e0-103">カスタム アダプターには、実装する必要のあるインターフェイスが 3 つあります。また、省略可能なインターフェイスも 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-103">There are three interfaces that custom adapters must implement, and two interfaces that are optional.</span></span>  
  
## <a name="mandatory-interfaces"></a><span data-ttu-id="aa4e0-104">必須のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa4e0-104">Mandatory interfaces</span></span>  
 <span data-ttu-id="aa4e0-105">アダプターはすべて、次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-105">All adapters must implement the following interfaces.</span></span>  
  
### <a name="ibasecomponent"></a><span data-ttu-id="aa4e0-106">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="aa4e0-106">IBaseComponent</span></span>  
 <span data-ttu-id="aa4e0-107">このインターフェイスの詳細、**名前**、**バージョン**、および**説明**アダプターのです。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-107">This interface details the **Name**, **Version**, and **Description** of the adapter.</span></span>  
  
### <a name="ibttransport"></a><span data-ttu-id="aa4e0-108">IBTTransport</span><span class="sxs-lookup"><span data-stu-id="aa4e0-108">IBTTransport</span></span>  
 <span data-ttu-id="aa4e0-109">このインターフェイスの詳細、**トランスポートの種類**と**ClassID**アダプターのです。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-109">This interface details the **Transport Type** and **ClassID** of the adapter.</span></span>  
  
### <a name="ibtbatchcallback"></a><span data-ttu-id="aa4e0-110">IBTBatchCallback</span><span class="sxs-lookup"><span data-stu-id="aa4e0-110">IBTBatchCallback</span></span>  
 <span data-ttu-id="aa4e0-111">このインターフェイスは、アダプターが、メッセージング エンジンに送信されるメッセージのバッチの状態やエラー情報を受信するコールバック インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-111">This interface is a callback interface through which the adapter receives status and error information for a batch of messages it submits to the Messaging Engine.</span></span>  
  
## <a name="optional-interfaces"></a><span data-ttu-id="aa4e0-112">省略可能なインターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa4e0-112">Optional interfaces</span></span>  
 <span data-ttu-id="aa4e0-113">次のインターフェイスは、必要に応じてアダプターに実装します。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-113">Adapters may or may not implement the following interfaces, depending on their needs.</span></span>  
  
### <a name="ipersistpropertybag"></a><span data-ttu-id="aa4e0-114">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="aa4e0-114">IPersistPropertyBag</span></span>  
 <span data-ttu-id="aa4e0-115">これは、ハンドラー構成がアダプターに送信されるときに使用される構成インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-115">This is a configuration interface through which handler configuration is delivered to the adapter.</span></span> <span data-ttu-id="aa4e0-116">このインターフェイスは、ハンドラー構成情報を持っているアダプターの場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-116">This interface is required only for adapters that have handler configuration information.</span></span>  
  
### <a name="ibttransportcontrol"></a><span data-ttu-id="aa4e0-117">IBTTransportControl</span><span class="sxs-lookup"><span data-stu-id="aa4e0-117">IBTTransportControl</span></span>  
 <span data-ttu-id="aa4e0-118">このインターフェイスはアダプターを初期化および終了するために使用します。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-118">This interface is used to initialize and terminate an adapter.</span></span> <span data-ttu-id="aa4e0-119">アダプターのトランスポート プロキシはこのインターフェイスを通じて渡されます。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-119">The adapter's transport proxy is passed to it through this interface.</span></span> <span data-ttu-id="aa4e0-120">このインターフェイスは、分離アダプターの場合は不要です。</span><span class="sxs-lookup"><span data-stu-id="aa4e0-120">This interface is not required for isolated adapters.</span></span>