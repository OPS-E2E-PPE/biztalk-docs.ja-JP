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
ms.openlocfilehash: 3161593fb871e93852480f717216391daac67e7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362419"
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
|  メッセージ テキスト   | BizTalk アセンブリの反映中にセキュリティ例外が発生しました"{0}"。 この問題は、アセンブリが共有ネットワーク フォルダーにある場合に発生する可能性があります。 この問題を解決するには、次のいずれかを試してください。1. アセンブリとその依存関係をローカル コンピューターにコピーします。 2. アクセスを許可するように、.NET 構成のランタイム セキュリティ ポリシーを調整します。 |
  
## <a name="explanation"></a>説明  
 適切な .NET ポリシーなしのネットワーク共有上にある BizTalk アセンブリを発行しようとして、このエラーが発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 エラー メッセージに記載されている特定の手順を実行できるだけでなく、ローカル アセンブリをコピーします。 または、ローカルのイントラネットに完全な信頼を付与するポリシーを編集します。  
  
 **コード アクセス セキュリティ ポリシー ツール (Caspol.exe) を使用します。**  
  
 通常のユーザーのアクセス許可を持つユーザー レベルで、ローカル コンピューター上のフォルダーに信頼を付与できます。 ネットワークの場所に信頼を付与するは、管理者特権を持っているし、コンピューター レベルでセキュリティ ポリシーを変更する必要があります。 コンピューター ポリシー レベルが、ユーザー ポリシー レベルとは無関係に機能し、場合でも、ユーザーのポリシーは、コンピューター ポリシー レベルがイントラネット ゾーンに完全な信頼を付与しません。 ポリシー レベルが一致する必要があります。  
  
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