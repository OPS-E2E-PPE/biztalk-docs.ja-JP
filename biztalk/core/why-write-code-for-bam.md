---
title: BAM のコードを記述する理由 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434f50a-e0a9-45e0-8c68-a059011e1296
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10b8ccb29d95daf8ccdf80d67faef3e50495af04
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="why-write-code-for-bam"></a><span data-ttu-id="96718-103">BAM のコードを記述する理由</span><span class="sxs-lookup"><span data-stu-id="96718-103">Why Write Code For BAM?</span></span>
<span data-ttu-id="96718-104">多くの場合、独自のコードを記述せずに BAM ツールを使用して追跡機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="96718-104">In most circumstances you can use the BAM tools without writing your own code to perform your tracking functions.</span></span> <span data-ttu-id="96718-105">これらのツールには、Excel 用の BAM アドイン、BAM 管理ユーティリティ、および追跡プロファイル エディター (TPE) があります。</span><span class="sxs-lookup"><span data-stu-id="96718-105">These tools are the BAM Add-in for Excel, the BAM Management utility, and the Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="96718-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM は、BizTalk オーケストレーションおよびメッセージング コンポーネント (パイプラインとポート) 用のインターセプターを提供します。</span><span class="sxs-lookup"><span data-stu-id="96718-106">BAM in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides interceptors for BizTalk orchestrations and messaging components (pipelines and ports).</span></span> <span data-ttu-id="96718-107">インターセプターは、構成ファイルに基づいて汎用的にデータを収集できるようにアプリケーションをインストルメント化するソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="96718-107">An interceptor is software that instruments an application so that it can collect data in a generic way based on a configuration file.</span></span> <span data-ttu-id="96718-108">追跡プロファイル エディターを使用して、これらのインターセプターを使用するようにアプリケーションをインストルメント化できます。</span><span class="sxs-lookup"><span data-stu-id="96718-108">You can instrument your application to use these interceptors by using the Tracking Profile Editor.</span></span> <span data-ttu-id="96718-109">追跡プロファイル エディターの詳細については、次を参照してください。[追跡プロファイル エディター](../core/tracking-profile-editor.md)です。</span><span class="sxs-lookup"><span data-stu-id="96718-109">For more information about the Tracking Profile Editor, see [Tracking Profile Editor](../core/tracking-profile-editor.md).</span></span>  
  
 <span data-ttu-id="96718-110">BAM API を使用したアプリケーションのインストルメント化が効果的であるのは、主に次の 2 つのシナリオです。</span><span class="sxs-lookup"><span data-stu-id="96718-110">There are two primary scenarios, however, in which you will find it advantageous to instrument your application using the BAM APIs:</span></span>  
  
-   <span data-ttu-id="96718-111">監視対象のホストに対して BAM インターセプターが存在しない場合</span><span class="sxs-lookup"><span data-stu-id="96718-111">There is no BAM interceptor for the host you intend to monitor.</span></span>  
  
-   <span data-ttu-id="96718-112">組み込みのインターセプターがアプリケーションの複雑さに対応しない場合</span><span class="sxs-lookup"><span data-stu-id="96718-112">The built-in interceptor does not allow for the complexity of your application.</span></span>  
  
 <span data-ttu-id="96718-113">組み込みのインターセプターが存在しない場合、BAM を使用することができます **EventStream** 関心のあるイベントをキャプチャする Api。</span><span class="sxs-lookup"><span data-stu-id="96718-113">When there is no built-in interceptor, you can use the BAM **EventStream** APIs to capture the events of interest.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96718-114">組み合わせることができます **EventStream** クラス、 **BAMInterceptor** 独自のインターセプターを作成するクラス。</span><span class="sxs-lookup"><span data-stu-id="96718-114">You can combine **EventStream** classes with the **BAMInterceptor** class to create your own interceptor.</span></span> <span data-ttu-id="96718-115">BAM API SDK のサンプルは、単純で拡張が可能な汎用インターセプターを示しています。</span><span class="sxs-lookup"><span data-stu-id="96718-115">The BAM API SDK sample illustrates a simple generic interceptor that you can extend.</span></span> <span data-ttu-id="96718-116">独自のインターセプターを作成して、各アプリケーションの新しいコードを記述しなくても多数の同様のプロセスをインストルメント化できます。</span><span class="sxs-lookup"><span data-stu-id="96718-116">By constructing your own interceptor you can instrument a number of similar processes without writing new code for each application.</span></span> <span data-ttu-id="96718-117">BAM API SDK のサンプルを表示するを参照してください。 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="96718-117">To view the BAM API SDK sample, see [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96718-118">参照</span><span class="sxs-lookup"><span data-stu-id="96718-118">See Also</span></span>  
 [<span data-ttu-id="96718-119">BAM ソリューションの実装</span><span class="sxs-lookup"><span data-stu-id="96718-119">Implementing BAM Solutions</span></span>](../core/implementing-bam-solutions.md)