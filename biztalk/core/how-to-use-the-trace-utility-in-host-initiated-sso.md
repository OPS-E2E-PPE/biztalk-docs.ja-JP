---
title: 側開始 SSO のホストで Trace ユーティリティを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed0b0a77881cba6de26454f51c6f6f8e21103e90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333170"
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a><span data-ttu-id="b3214-102">側開始 SSO のホストで Trace ユーティリティを使用する方法</span><span class="sxs-lookup"><span data-stu-id="b3214-102">How to Use the Trace Utility in Host Initiated SSO</span></span>
<span data-ttu-id="b3214-103">トラブルシューティングの主要な方法をトレースしています。</span><span class="sxs-lookup"><span data-stu-id="b3214-103">The primary method of troubleshooting is tracing.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="b3214-104">追跡</span><span class="sxs-lookup"><span data-stu-id="b3214-104">Tracing</span></span>  
 <span data-ttu-id="b3214-105">SSO でトレースを有効にするのにには、トレースのコマンド ライン ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3214-105">Use the Trace command line utility to enable tracing in SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3214-106">トレース コマンドが動作する次のディレクトリにファイル tracelog.exe 必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3214-106">For the trace command to function, the file tracelog.exe must be in the following directory:</span></span>  
>   
>  <span data-ttu-id="b3214-107">\<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="b3214-107">\<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3214-108">このファイルは、次の場所からダウンロードできます。 [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span><span class="sxs-lookup"><span data-stu-id="b3214-108">You can download this file from the following location: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span></span>  
  
#### <a name="to-use-the-trace-utility"></a><span data-ttu-id="b3214-109">トレース ユーティリティを使用するには</span><span class="sxs-lookup"><span data-stu-id="b3214-109">To use the trace utility</span></span>  
  
1.  <span data-ttu-id="b3214-110">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3214-110">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b3214-111">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b3214-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b3214-112">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b3214-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b3214-113">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="b3214-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b3214-114">型**Trace – start – high**高 に、トレース レベルを設定し、トレースを開始します。</span><span class="sxs-lookup"><span data-stu-id="b3214-114">Type **Trace –start –high** to set the tracing level to high and begin the trace.</span></span>  
  
5.  <span data-ttu-id="b3214-115">側開始 SSO のホストでシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3214-115">Run the scenario with host initiated SSO.</span></span>  
  
6.  <span data-ttu-id="b3214-116">型**Trace – 停止**トレースを終了します。</span><span class="sxs-lookup"><span data-stu-id="b3214-116">Type **Trace –stop** to end the trace.</span></span> <span data-ttu-id="b3214-117">ディレクトリの上、分析のため Microsoft に送信することができますに .bin ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b3214-117">A .bin file is generated in the directory above, which you can send to Microsoft for analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3214-118">参照</span><span class="sxs-lookup"><span data-stu-id="b3214-118">See Also</span></span>  
 [<span data-ttu-id="b3214-119">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="b3214-119">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)