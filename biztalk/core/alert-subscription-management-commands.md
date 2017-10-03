---
title: "アラートのサブスクリプション管理コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cd6ad27-6217-466a-b616-4b26fb31b0af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914d5cd9ac19e160c1f26df3f762f81fb89345d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="alert-subscription-management-commands"></a>警告サブスクリプション管理コマンド
BAM 管理ユーティリティのサブスクリプション管理コマンドを使用すると、警告サブスクリプションを操作することができます。  
  
-   get サブスクリプション: サブスクライバーは、アラートの一覧を取得します。  
  
-   サブスクリプションの追加: アラートにサブスクライバーを追加します。  
  
-   削除するサブスクリプション: サブスクライバーを警告から削除します。  
  
> [!NOTE]
>  含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で & #124 オフ**パラメーター スイッチ。 Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。 このスイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-subscription-command"></a>get-subscription コマンド  
 **使用方法**  
  
 **bm.exe get サブスクリプション-ビュー:\<ビュー名 >-警告:\<警告名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名 >|指定できますが、アラート ビューの名前。|  
|警告:\<警告名 >|サブスクリプションを取得する警告の名前です。|  
|サーバー:\<サーバー >|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース >|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定した警告のすべてのサブスクライバーを一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a>add-subscription コマンド  
 **使用方法**  
  
 **bm.exe - サブスクリプションの追加-ビュー:\<ビュー名 >-警告:\<警告名 >-accountname:\<アカウント名 >-型: [ファイル (&) #124 です。Email] [-電子メール:\<電子メール アドレス >] [-サーバー:\<サーバー >] [-データベース:\<データベース >]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名 >|警告が指定されたビューの名前です。|  
|警告:\<警告名 >|サブスクライブする警告の名前です。|  
|AccountName:\<アカウント名 >|警告をサブスクライブするアカウント (domain\user 形式) です。|  
|型: [ファイル (&) #124 です。電子メール]|警告の配信方法です。 配信方法として電子メールを指定した場合は、Email パラメーターも指定する必要があります。|  
|電子メール:\<電子メール アドレス >|省略可能: アラートの通知を配信する電子メール アドレス。|  
|サーバー:\<サーバー >|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース >|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定したアカウントに対し、特定の警告に対するサブスクリプションを追加します。  
  
 **使用例**  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a>remove-subscription コマンド  
 **使用方法**  
  
 **bm.exe 削除-サブスクリプション-ビュー:\<ビュー名 >-警告:\<警告名 >-accountname:\<アカウント名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ビュー:\<ビュー名 >|警告が指定されたビューの名前です。|  
|警告:\<警告名 >|警告の名前を指定します。|  
|AccountName:\<アカウント名 >|警告から削除するアカウント (domain\user 形式) です。|  
|サーバー:\<サーバー >|省略可能: ビューが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース >|省略可能: ビューが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 特定の警告から、指定したアカウントのサブスクリプションを削除します。 指定されたアカウントのすべてのサブスクリプションが削除されます。  
  
 **使用例**  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)