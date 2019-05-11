---
title: HTTP アダプターに関する問題を診断する方法 |Microsoft Docs
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
ms.openlocfilehash: 1496ed936629a502d9274800455fd79334260f51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385250"
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a>HTTP アダプターに関する問題の診断方法
このセクションには、HTTP アダプターに関する問題の診断に役立つことができますの手順が含まれています。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>IIS および HTTPERR ログ ファイルの IIS サーバーのエラーを確認してください。  
  
- ソースまたはターゲット IIS サーバーのログ ファイルは、HTTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。 既定では、IIS は Windows Server 上のログ ファイルは次のディレクトリにあります。  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
   既定では、HTTPERR ログ ファイル、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]ベースのコンピューターは、次のディレクトリに配置されます。  
  
   <em>%WinDir%\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  HTTPERR ログ ファイルは上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a>System.Net.HttpWebRequest クラスを使用するクライアントで送信先 URL への投稿の HTTP 送信アダプターに関する問題を分離します。  
  
1.  HTTP 送信アダプターには、送信先 URL に投稿するときにエラーが生成している場合、は、送信先 URL に投稿する、System.Net.HttpWebRequest クラスおよび HttpWebResponse クラスを使用するクライアントを作成します。 このアプローチは、問題が、HTTP 送信アダプターに固有であるか、一般に、送信先 URL への問題の投稿がある場合かを確認に役立ちます。  
  
2.  詳細については、System.Net.HttpWebRequest クラスおよび HttpWebResponse クラスを使用するクライアントを作成する方法を参照してください。[新しい System.Net クラスを使用して HTTP クライアントを作成する方法](http://go.microsoft.com/fwlink/?LinkId=66987)します。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [HTTP アダプターのトラブルシューティング](../core/troubleshooting-the-http-adapter.md)