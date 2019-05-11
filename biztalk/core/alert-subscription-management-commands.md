---
title: 警告サブスクリプション管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cd6ad27-6217-466a-b616-4b26fb31b0af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ffcfea22ac63f3a8f4eb22aaeeae3513705ab2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359274"
---
# <a name="alert-subscription-management-commands"></a>警告サブスクリプション管理コマンド
BAM 管理ユーティリティのサブスクリプション管理コマンドを使用すると、警告のサブスクリプションを使用できます。  
  
-   get サブスクリプション:警告のサブスクライバーの一覧を取得します。  
  
-   追加のサブスクリプション:アラートには、サブスクライバーを追加します。  
  
-   サブスクリプションの削除:アラートから、サブスクライバーを削除します。  
  
> [!NOTE]
>  含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。 トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。 スイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-subscription-command"></a>get-subscription コマンド  
 **使用方法**  
  
 **bm.exe の get サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|指定する、アラートがビューの名前。|  
|アラート:\<アラート名\>|サブスクリプションの取得元となるアラートの名前。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定した警告へのすべてのサブスクライバーを一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a>サブスクリプションの追加コマンド  
 **使用方法**  
  
 **bm.exe の追加-サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>-accountname:\<アカウント名\>-型: [ファイル&#124;電子メール] [-電子メール:\<電子メールアドレス\>] [-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|アラートが指定されているビューの名前。|  
|アラート:\<アラート名\>|サブスクライブするアラートの名前。|  
|AccountName:\<アカウント名\>|Domain \user 形式で警告をサブスクライブするアカウントです。|  
|種類: [ファイル&#124;メール]|警告の配信の種類。 電子メールの配信の種類を指定する場合は、コマンドラインで電子メールのパラメーターを含める必要があります。|  
|電子メール:\<電子メール アドレス\>|省略可能:アラート通知の配信先の電子メール アドレス。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定した警告には、指定されたアカウントのサブスクリプションを追加します。  
  
 **使用例**  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a>remove-subscription コマンド  
 **使用方法**  
  
 **bm.exe の削除-サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>-accountname:\<アカウント名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ビュー:\<ビュー名\>|アラートが指定されているビューの名前。|  
|アラート:\<アラート名\>|警告の名前を指定します。|  
|AccountName:\<アカウント名\>|Domain \user 形式で、警告から削除するアカウントです。|  
|サーバー:\<サーバー\>|省略可能:ビューが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ビューが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定された警告から、指定されたアカウントのサブスクリプションを削除します。 指定されたアカウントのすべてのサブスクリプションが削除されます。  
  
 **使用例**  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)