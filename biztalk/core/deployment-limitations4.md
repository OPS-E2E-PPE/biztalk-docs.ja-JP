---
title: "展開 Limitations4 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, limitations
ms.assetid: 1312627e-9de2-461e-a8c4-66a9d41bb714
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d8e33c7274ab0f95c6d7fff1bf9746ac86e420
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>展開の制限事項
によってエクスポートされるバインド ファイル (*) の星トランスポート アダプターのパスワードが格納されている、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、され、同じ形式で管理コンポーネントに渡されます。 アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してのパスワードを入力する必要があります。  
  
 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。  
  
> [!NOTE]
>  .Msi ファイルをインポートするときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise アダプターのいずれかのバインド情報を含むアプリケーションをインポート エラー メッセージを受信する可能性があります。 サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[http://go.microsoft.com/fwlink/?LinkId=196087](http://go.microsoft.com/fwlink/?LinkId=196087)です。  
  
## <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 パスワードの制限を回避するには、次の操作を実行します。  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限の問題を回避するには  
  
1.  パスワードではなく、エンタープライズ シングル サインオンを使用します。 SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。  
  
2.  論理システムと送信および受信サービスを確認します。  
  
## <a name="see-also"></a>参照  
 [ポートとアセンブリの展開](../core/deploying-ports-and-assemblies3.md)