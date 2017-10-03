---
title: "展開 Limitations2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deployment, limitations
- passwords, adapter limitations
ms.assetid: 9db2ca70-5db2-4b14-a898-13049737c188
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05fa9704823bd7e9df9f0bc7d4516719a8a490e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>展開の制限事項
アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) が BizTalk 展開ウィザードによってエクスポートし、管理に渡されるバインド ファイルに同じ形式でコンポーネントです。 アスタリスクをランダムな英数字の値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力し、**トランスポートのプロパティ**バインド ファイルをインポートした後のページです。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してのパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。  
  
> [!NOTE]
>  .Msi ファイルをインポートするときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise アダプターのいずれかのバインド情報を含むアプリケーションをインポート エラー メッセージを受信する可能性があります。 サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us)です。  
  
## <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 パスワードの制限への対処方法として、次のいずれかの方法を使用します。  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限の問題を回避するには  
  
1.  アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。  
  
    > [!CAUTION]
    >  これは、セキュリティ上の理由により推奨されていません。  
  
2.  アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後のページです。  
  
    > [!NOTE]
    >  この回避する場合のみ使用できます、ターゲット コンピューター上またはカスタム ツールを開発することにより、Microsoft Visual Studio がインストールされています。  
  
 **- または -**  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限の問題を回避するには  
  
1.  パスワードではなく、エンタープライズ シングル サインオンを使用します。  
  
     SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。  
  
2.  論理システムと送信および受信サービスを確認します。  
  
## <a name="see-also"></a>参照  
 [JD Edwards OneWorld トランスポートのプロパティを設定する方法](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)   
 [ポートとアセンブリの展開](../core/deploying-ports-and-assemblies4.md)