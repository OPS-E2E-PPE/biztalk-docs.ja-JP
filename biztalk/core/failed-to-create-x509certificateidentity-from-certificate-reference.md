---
title: 証明書参照から X509CertificateIdentity を作成できませんでした |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3acee8e-c035-4e58-8bfc-397885b4d185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b991f9acb2b5cc193d24d36e1a5de8650e7af72b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988931"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a>証明書参照から X509CertificateIdentity を作成できませんでした
## <a name="details"></a>詳細  

|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| 製品バージョン |                                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                         |
|    イベント ID     |                                                                     0                                                                      |
|  イベント ソース   |                                                                     0                                                                      |
|    コンポーネント    |                                                                     0                                                                      |
|  シンボル名  |                                                                     0                                                                      |
|  メッセージ テキスト   | 証明書参照から X509CertificateIdentity を作成できませんでした。 (StoreName ={0}、StoreLocation ={1}、X509FindType ={2}、FindValue ="{3}") |

## <a name="explanation"></a>説明  
 このエラーは、アダプターで、エンドポイント ID 構成に指定されている X509Certificate の作成に失敗したことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 証明書参照設定を確認するには、次の手順を実行します。  

#### <a name="to-configure-the-certificate-reference-settings"></a>証明書参照設定を構成するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを特定し、次にトランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. クリックして**構成**します。  

8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  

9. **エンドポイント Id**セクションで、**を編集します。**  

10. **Id エディター**  ダイアログ ボックスで、いることを確認、**証明書参照**設定が無効です。
