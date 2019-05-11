---
title: SSO の SSL を有効にする方法 |Microsoft Docs
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
ms.openlocfilehash: 8478f688dc504ba64690f6f7b8d2a0faa4b31feb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337930"
---
# <a name="how-to-enable-ssl-for-sso"></a><span data-ttu-id="9f367-102">SSO の SSL を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="9f367-102">How to Enable SSL for SSO</span></span>
<span data-ttu-id="9f367-103">すべてのエンタープライズ シングル サインオン (SSO) サーバーと SSO データベース間で Secure Sockets Layer (SSL) を有効にするのにには、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f367-103">Use this command to enable Secure Sockets Layer (SSL) between all the Enterprise Single Sign-On (SSO) servers and the SSO database.</span></span>  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a><span data-ttu-id="9f367-104">エンタープライズ シングル サインオンの SSL を有効にするには</span><span class="sxs-lookup"><span data-stu-id="9f367-104">To enable SSL for Enterprise Single Sign-On</span></span>  
  
1.  <span data-ttu-id="9f367-105">クリックして**開始**、 をクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="9f367-105">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="9f367-106">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9f367-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9f367-107">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="9f367-107">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="9f367-108">型**ssoconfig – setSSL\<はい/いいえ\>** ここで、 \<**はい/いいえ**\> SSO システムで SSL を有効にするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9f367-108">Type **ssoconfig –setSSL \<yes/no\>**, where \<**yes/no**\> indicates whether you want to enable SSL in the SSO system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f367-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f367-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f367-110">参照</span><span class="sxs-lookup"><span data-stu-id="9f367-110">See Also</span></span>  
 [<span data-ttu-id="9f367-111">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="9f367-111">Using SSO</span></span>](../core/using-sso.md)