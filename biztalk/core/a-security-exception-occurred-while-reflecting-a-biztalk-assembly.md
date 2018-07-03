---
title: BizTalk アセンブリの反映中にセキュリティ例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 301b85c7-8e67-482e-8666-67a91ca5c73d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d07b1e5788ae696e94a3bbe326f2cfe79d1b76f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979931"
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a>BizTalk アセンブリの反映中にセキュリティ例外が発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                 |
| 製品バージョン |                                                                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                             |
|    イベント ID     |                                                                                                                                                                         0                                                                                                                                                                          |
|  イベント ソース   |                                                                                                                                                                         0                                                                                                                                                                          |
|    コンポーネント    |                                                                                                                                                                         0                                                                                                                                                                          |
|  シンボル名  |                                                                                                                                                                         0                                                                                                                                                                          |
|  メッセージ テキスト   | BizTalk アセンブリの反映中にセキュリティ例外が発生しました"{0}"。 この問題は、アセンブリが共有ネットワーク フォルダーに格納されている場合に発生する可能性があります。 この問題を修正する、次のいずれかの操作を試してください: 1。 アセンブリとその依存関係をローカル コンピューターにコピーします。 2. .NET 構成のランタイム セキュリティ ポリシーを調整して、アクセスできるようにします。 |
  
## <a name="explanation"></a>説明  
 このエラーは、適切な .NET ポリシーが設定されていない状態で、ネットワーク共有上にある BizTalk アセンブリを発行しようとするときに発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 エラー メッセージに指定された手順を実行し、さらにアセンブリをローカルにコピーします。 または、ローカル イントラネットに完全信頼を付与するようにポリシーを編集します。  
  
 **コード アクセス セキュリティ ポリシー ツール (Caspol.exe) を使用します。**  
  
 通常のユーザー アクセス許可では、ユーザー レベルでローカル コンピューターのフォルダーに信頼を付与できます。 ネットワークの場所に信頼を付与するには、管理者特権が必要です。また、コンピューター レベルでセキュリティ ポリシーを変更する必要があります。 コンピューター ポリシー レベルは、ユーザー ポリシー レベルとは関係なく動作するため、コンピューター ポリシー レベルでは、ユーザー ポリシーとは異なり、イントラネット ゾーンに完全信頼を付与しません。 ポリシー レベルは一致する必要があります。  
  
 **ローカル フォルダーに完全な信頼を付与するには**  
  
-   Visual Studio コマンド プロンプトで次のコマンドを入力します。  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 **ネットワーク フォルダーへの完全な信頼を付与するには**  
  
-   Visual Studio コマンド プロンプトで次のコマンドを入力します。  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```