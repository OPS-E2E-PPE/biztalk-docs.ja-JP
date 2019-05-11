---
title: ローカル ユーザー非 Windows アプリケーションにログオンする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55957f4-22c4-48b5-827a-ab41d8f846ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3a403ff5e5d31b807e443377b0ca7954dd74efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384751"
---
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a>ローカル ユーザー非 Windows アプリケーションにログオンする方法
関連アプリケーションでユーザーを設定した後は、外部ユーザー名と、現在のユーザーの資格情報にアクセスするのにシングル サインオン (SSO) を使用することができます。 これらの資格情報を使用して、ユーザーは、ホスト サーバーで実行されている関連アプリケーションにログオンし、ログオンできます。  
  
> [!NOTE]
>  Sso には、適切なセキュリティ プロトコルを設定するだけでなく、適切なセキュリティ コンテキストで SSO を呼び出すようにアプリケーションを許可する追加のセキュリティを設定する可能性がありますも必要です。 アプリケーションでは、適切なセキュリティ コンテキストで SSO を呼び出すことはできません、SSO により、アプリケーションへのアクセスが拒否されます。  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a>SSO アプリケーションのセキュリティ コンテキストを設定するには  
  
1.  資格情報を正常に実行するアプリケーションのニーズを特定します。  
  
     たとえば、Web サービスまたは IIS でホストされている .NET Framework リモート処理を使用するアプリケーションは、SSO に適切な資格情報を渡すためにクライアントを偽装する必要があります。  
  
2.  これらの資格情報を使用してアプリケーションを提供する仮想ディレクトリ、アプリケーション プール、および web.config ファイルであるよう、関連するセキュリティ設定を設定することを確認します。  
  
     セキュリティ資格情報を設定する方法の詳細については、次を参照してください[Building Secure ASP.NET Applications:。認証、承認、およびセキュリティで保護された通信](http://go.microsoft.com/fwlink/?LinkId=193906)します。  
  
     ASP.NET Web サービスの資格情報の詳細については、次を参照してください[HOW TO:。ASP.NET Web サービスに現在の資格情報を渡す](http://go.microsoft.com/fwlink/?LinkId=193907)します。  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a>ローカル ユーザー、ホスト アプリケーションにログオンする  
  
1.  ホスト サーバーで実行されているアプリケーションは、現在のユーザーのログイン要求を受け取ります。  
  
     ホスト アプリケーションにログオンする、現在のユーザーの要求を特定するユーザーの責任になります。  
  
2.  使用している現在のユーザーの資格情報を取得`ISSOLookup1.GetCredentials`または`ISSOLookup2.GetCredentials`します。  
  
     関連フラグと共に、ホスト アプリケーションの名前を指定する必要があります。 `GetCredentials` 関連付けられたユーザー名とホスト アプリケーションの資格情報を返します。  
  
     使用しますか`ISSOLookup1`または`ISSOLookup2`します。 唯一の違いは`ISSOLookup2`ローカル windows アプリケーションへのリモート ユーザーがログインするためのメソッドがあります。  
  
3.  ホスト アプリケーションにログオンするには、外部ユーザー名と資格情報を使用します。  
  
     適切に資格情報を使用して、ホスト アプリケーションにログオンする方法を決定することをお勧めします。  
  
## <a name="see-also"></a>参照  
 [リモート ユーザー アプリケーションをローカルにログオンする方法](../core/how-to-log-a-remote-user-on-to-a-local-application.md)