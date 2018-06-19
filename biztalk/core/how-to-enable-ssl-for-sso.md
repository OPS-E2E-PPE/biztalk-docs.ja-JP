---
title: SSO の SSL を有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, SSL
- managing [SSO], enabling SSL
- SSL
ms.assetid: 0d75962a-a0b0-4e69-8001-54e7df617006
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cd617fd955100930b513bc6c364626e4912eb81
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969912"
---
# <a name="how-to-enable-ssl-for-sso"></a><span data-ttu-id="d3192-102">SSO の SSL を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="d3192-102">How to Enable SSL for SSO</span></span>
<span data-ttu-id="d3192-103">このコマンドを使用すると、すべてのエンタープライズ シングル サインオン (SSO) サーバーと SSO データベース間で Secure Sockets Layer (SSL) を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d3192-103">Use this command to enable Secure Sockets Layer (SSL) between all the Enterprise Single Sign-On (SSO) servers and the SSO database.</span></span>  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a><span data-ttu-id="d3192-104">エンタープライズ シングル サインオンで SSL を有効にするには</span><span class="sxs-lookup"><span data-stu-id="d3192-104">To enable SSL for Enterprise Single Sign-On</span></span>  
  
1.  <span data-ttu-id="d3192-105">をクリックして**開始**、 をクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="d3192-105">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d3192-106">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d3192-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d3192-107">既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="d3192-107">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d3192-108">型**ssoconfig – setSSL\<はい/いいえ\>** ここで、 \<**はい/いいえ**\> SSO システムで SSL を有効にするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d3192-108">Type **ssoconfig –setSSL \<yes/no\>**, where \<**yes/no**\> indicates whether you want to enable SSL in the SSO system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3192-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3192-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3192-110">参照</span><span class="sxs-lookup"><span data-stu-id="d3192-110">See Also</span></span>  
 [<span data-ttu-id="d3192-111">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="d3192-111">Using SSO</span></span>](../core/using-sso.md)