---
title: "ローカル ユーザー、Windows 以外のアプリケーションにログオンする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b55957f4-22c4-48b5-827a-ab41d8f846ac
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3c2e9ffaede20e29987938a436ad2a091920fce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a>ローカル ユーザー、Windows 以外のアプリケーションにログオンする方法
関連アプリケーションでユーザーを設定すると、シングル サインオン (SSO) を使用して、現在のユーザーの外部ユーザー名および資格情報にアクセスできます。 これらの資格情報を使用することにより、ホスト サーバーで実行されている関連アプリケーションにユーザーをログオンさせることができます。  
  
> [!NOTE]
>  アプリケーションが正しいセキュリティ コンテキストで SSO を呼び出せるようにするには、SSO に対する適切なセキュリティ プロトコルの設定に加えて、追加のセキュリティ設定が必要になる場合があります。 アプリケーションが正しいセキュリティ コンテキストで SSO を呼び出せない場合、アプリケーションへのアクセスが SSO によって拒否されます。  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a>SSO アプリケーションのセキュリティ コンテキストを設定するには  
  
1.  アプリケーションが正常に動作するために必要な資格情報を特定します。  
  
     たとえば、Web サービスまたは IIS でホストされている .NET Framework リモート処理を使用するアプリケーションでは、SSO に適切な資格情報を渡すために、クライアントを偽装する必要があります。  
  
2.  関連するセキュリティ設定 (仮想ディレクトリ、アプリケーション プール、web.config ファイルなどのセキュリティ設定) が、これらの資格情報をアプリケーションに提供するように設定されていることを確認します。  
  
     セキュリティ資格情報を設定する方法の詳細については、次を参照してください。[セキュリティで保護された ASP.NET アプリケーションの構築: 認証、承認、およびセキュリティ保護された通信](http://go.microsoft.com/fwlink/?LinkId=193906)です。  
  
     ASP.NET Web サービスの資格情報の詳細については、次を参照してください。 [HOW TO: 渡す現在の資格情報を ASP.NET Web サービス](http://go.microsoft.com/fwlink/?LinkId=193907)です。  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a>ローカル ユーザーがホスト アプリケーションにログオンするには  
  
1.  ホスト サーバーで実行されているアプリケーションに現在のユーザーをログオンするための要求を受け取ります。  
  
     ホスト アプリケーションへのログオンをユーザーが要求する方法は、適切に決定してください。  
  
2.  `ISSOLookup1.GetCredentials` または `ISSOLookup2.GetCredentials` を使用している現在のユーザーの資格情報を取得します。  
  
     関連フラグと共に、ホスト アプリケーションの名前を指定する必要があります。 `GetCredentials`関連付けられたユーザー名とホスト アプリケーションの資格情報を返します。  
  
     `ISSOLookup1` または `ISSOLookup2` を使用できます。 この 2 つの違いは、`ISSOLookup2` には、リモート ユーザーによるローカル Windows アプリケーションへのログオン方法も含まれている点です。  
  
3.  外部ユーザー名と資格情報を使用して、ホスト アプリケーションにログオンします。  
  
     資格情報を使用してホスト アプリケーションにログオンする方法は、適切に決定してください。  
  
## <a name="see-also"></a>参照  
 [リモート ユーザー、ローカルのアプリケーションにログオンする方法](../core/how-to-log-a-remote-user-on-to-a-local-application.md)