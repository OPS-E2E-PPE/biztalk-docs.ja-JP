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
ms.openlocfilehash: 6cb054a9e062eed58d8fe7469254301f416d7ed0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345945"
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
|  メッセージ テキスト   | 証明書参照から X509CertificateIdentity を作成できませんでした。 (StoreName={0}, StoreLocation={1}, X509FindType={2}, FindValue="{3}") |

## <a name="explanation"></a>説明  
 このエラーは、アダプターがエンドポイントの id 構成に指定されている X509Certificate の作成に失敗したことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 証明書参照設定を確認するのにには、次の手順を使用します。  

#### <a name="to-configure-the-certificate-reference-settings"></a>証明書参照設定を構成するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. をクリックして**構成**です。  

8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  

9. **エンドポイント Id**セクションで、**を編集します。**  

10. **Id エディター**  ダイアログ ボックスで、いることを確認、**証明書参照**設定が無効です。
