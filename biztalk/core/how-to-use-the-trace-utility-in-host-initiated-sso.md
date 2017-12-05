---
title: "側開始 SSO のホストで、トレース ユーティリティを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb2003cc6091e3f14bd863902e03649d9005722
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a><span data-ttu-id="8b16c-102">側開始 SSO のホストで、トレース ユーティリティを使用する方法</span><span class="sxs-lookup"><span data-stu-id="8b16c-102">How to Use the Trace Utility in Host Initiated SSO</span></span>
<span data-ttu-id="8b16c-103">トラブルシューティングの主要な方法はトレースを行うことです。</span><span class="sxs-lookup"><span data-stu-id="8b16c-103">The primary method of troubleshooting is tracing.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="8b16c-104">追跡</span><span class="sxs-lookup"><span data-stu-id="8b16c-104">Tracing</span></span>  
 <span data-ttu-id="8b16c-105">SSO でトレースを有効にするには Trace コマンド ライン ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b16c-105">Use the Trace command line utility to enable tracing in SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b16c-106">Trace コマンドが動作するためには、tracelog.exe ファイルが次のディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b16c-106">For the trace command to function, the file tracelog.exe must be in the following directory:</span></span>  
>   
>  <span data-ttu-id="8b16c-107">\<*ドライブ*\>: \program files \common files \enterprise シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8b16c-107">\<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b16c-108">このファイルは、次の場所からダウンロードできます: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span><span class="sxs-lookup"><span data-stu-id="8b16c-108">You can download this file from the following location: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span></span>  
  
#### <a name="to-use-the-trace-utility"></a><span data-ttu-id="8b16c-109">Trace ユーティリティを使用するには</span><span class="sxs-lookup"><span data-stu-id="8b16c-109">To use the trace utility</span></span>  
  
1.  <span data-ttu-id="8b16c-110">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b16c-110">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="8b16c-111">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="8b16c-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8b16c-112">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="8b16c-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="8b16c-113">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="8b16c-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="8b16c-114">型**Trace – start – 高**高 に、トレース レベルを設定し、トレースを開始します。</span><span class="sxs-lookup"><span data-stu-id="8b16c-114">Type **Trace –start –high** to set the tracing level to high and begin the trace.</span></span>  
  
5.  <span data-ttu-id="8b16c-115">ホスト側開始 SSO でシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b16c-115">Run the scenario with host initiated SSO.</span></span>  
  
6.  <span data-ttu-id="8b16c-116">型**Trace – 停止**トレースを終了します。</span><span class="sxs-lookup"><span data-stu-id="8b16c-116">Type **Trace –stop** to end the trace.</span></span> <span data-ttu-id="8b16c-117">.bin ファイルが上記のディレクトリに生成されます。このファイルは、分析のためにマイクロソフトに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="8b16c-117">A .bin file is generated in the directory above, which you can send to Microsoft for analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b16c-118">参照</span><span class="sxs-lookup"><span data-stu-id="8b16c-118">See Also</span></span>  
 [<span data-ttu-id="8b16c-119">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="8b16c-119">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)