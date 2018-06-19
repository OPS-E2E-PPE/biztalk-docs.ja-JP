---
title: HTTP アダプターに関する問題を診断する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91f818dd-11fa-4ea4-b904-e8e00b3e49b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 545e095624c30b4611c74dcfbdead13d685164ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249842"
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a>HTTP アダプターに関する問題の診断方法
ここでは HTTP アダプターに関する問題の診断手順について説明します。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>IIS サーバーの IIS ログ ファイルと TTPERR ログ ファイルでエラーを確認する  
  
-   ソースまたはターゲットの IIS サーバー ログ ファイルには、HTTP アダプターに関する問題のトラブルシューティングに役立つ情報が含まれています。 既定では、Windows Server の IIS ログ ファイルは、次のディレクトリにあります。  
  
     *%Windir%\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
     既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。  
  
     *%Windir%\\*system32\LogFiles\HTTPERR\  
  
    > [!NOTE]
    >  HTTPERR ログ ファイルが上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a>System.Net.HttpWebRequest クラスを使用するクライアントを送信先 URL に POST して、HTTP 送信アダプターの問題を切り分ける  
  
1.  送信先 URL への POST を実行したときに HTTP 送信アダプターでエラーが生成される場合は、System.Net.HttpWebRequest クラスと HttpWebResponse クラスを使用するクライアントを作成して送信先 URL に POST します。 この方法は、問題が HTTP 送信アダプター限定のものであるか、送信先 URL への POST に関する一般的なものであるかを判断するのに役立ちます。  
  
2.  System.Net.HttpWebRequest クラスおよび HttpWebResponse クラスを使用するクライアントの作成の詳細については、次を参照してください。[新しい System.Net クラスを使用して HTTP クライアントを作成する方法](http://go.microsoft.com/fwlink/?LinkId=66987)です。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [HTTP アダプターのトラブルシューティング](../core/troubleshooting-the-http-adapter.md)