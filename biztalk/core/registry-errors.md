---
title: レジストリ エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5bf2cd-f807-4083-8687-4416a2ee2908
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afca0825ee04334385925d08e3edb0d0ed055c19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398000"
---
# <a name="registry-errors"></a>レジストリ エラー
診断および WCF のレジストリ エラーを解決するための情報です。  

## <a name="failed-to-access-the-registry"></a>レジストリにアクセスできませんでした
  
|                 |                                   エラーの詳細                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                             HKLM を開けませんでした。\\{0}します。                              |
  
### <a name="explanation"></a>説明  
 このエラーは、レジストリへのアクセスに失敗したことを示します。  
  
### <a name="user-action"></a>ユーザーの操作  
 レジストリに読み取りアクセス権があることを確認します。 レジストリにアクセスするには、管理者特権があるか、コンピューターの管理者を確認してください。
 
## <a name="failed-to-obtain-biztalk-install-path"></a>BizTalk のインストール パスを取得できませんでした
  
|                 |                                   エラーの詳細                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |             HKLM から BizTalk のインストール パスを取得できませんでした。\\{0}\\{1}              |
  
## <a name="explanation"></a>説明  
 このエラーは、レジストリへのアクセス失敗を示します、およびキー値が正しくありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 レジストリに読み取りアクセス権があることを確認します。 キーが正しい値を確認します。 レジストリにアクセスするには、管理者特権があるか、コンピューターの管理者を確認してください。 