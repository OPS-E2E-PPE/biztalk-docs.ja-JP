---
title: "展開 Limitations3 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, password limitations
- transport adapter password
ms.assetid: 79cd330f-ecc5-430e-9d79-608593d873cb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0d01947e0769189c269a1853e7fda0e11cedb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>展開の制限事項
トランスポート アダプターのパスワードは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってエクスポートされるバインド ファイルにアスタリスク (******) で保存され、同じ形式で管理コンポーネントに渡されます。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が完了した後、バインド ファイルからパスワードを削除する必要があります。  
  
> [!NOTE]
>  .Msi ファイルをインポートするときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise アダプターのいずれかのバインド情報を含むアプリケーションをインポート エラー メッセージを受信する可能性があります。 サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087)です。  
  
## <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 このパスワードの制限に対処するには、次のいずれかの方法を使用します。  
  
-   アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。  
  
    > [!CAUTION]
    >  この操作は、セキュリティ上の理由により推奨されていません。  
  
-   アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。  
  
    > [!NOTE]
    >  この対処方法を使用できるのは、対象のコンピューターに Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされているか、カスタム ツールを開発する場合のみです。  
  
 -または-  
  
-   パスワードではなく、エンタープライズ シングル サインオン (SSO) を使用します。  
  
     SSO オプションを使用するには、バインド ファイルをインポートする必要があります。  
  
 論理システムと送信を確認し、サービスを受信します。  
  
## <a name="see-also"></a>参照  
 [ポートとアセンブリの展開](../core/deploying-ports-and-assemblies5.md)