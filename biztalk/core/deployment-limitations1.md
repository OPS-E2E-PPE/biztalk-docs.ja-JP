---
title: "展開 Limitations1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deployment, limitations
ms.assetid: a984ccce-37b2-4738-b652-7232a18e0510
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65fb1c1a1211865b07c3abb987f0a1d31fbfd69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>展開の制限事項
個の星トランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) BizTalk Server によってエクスポートされるバインド ファイルにされ、同じ管理コンポーネントに渡されます形式です。 アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。  
  
 これは、既知の制限です。 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションでエンタープライズ アダプターのバインド情報を含む .msi ファイルをインポートするときに、インポート エラー メッセージが表示されることがあります。 サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087)です。  
  
## <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 このパスワードの制限に対処するには、次のいずれかの方法を使用します。  
  
-   アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。  
  
> [!CAUTION]
>  これは、セキュリティ上の理由により推奨されていません。  
  
-   アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。  
  
> [!NOTE]
>  この対処方法を使用できるのは、対象のコンピューターに Visual Studio がインストールされているか、カスタム ツールを開発する場合のみです。  
  
-   論理システムと送信および受信サービスを確認します。  
  
## <a name="see-also"></a>参照  
 [ポートとアセンブリの展開](../core/deploying-ports-and-assemblies2.md)