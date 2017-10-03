---
title: "UninstallApp コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea94335882ffbcf01b69c450ef4a5eb80ef4fa3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="uninstallapp-command"></a>UninstallApp コマンド
BizTalk アプリケーションをローカル コンピューターからアンインストールし、さらに、コントロール パネルの [プログラムの追加と削除] に表示されるプログラム一覧からも削除します。 このコマンドの実行結果は、[プログラムの追加と削除] を使ってアプリケーションを削除した場合と同じです。 このアプリケーションに対して複数の .msi ファイルがインストールされている場合、これらの .msi ファイルによってインストールされたアイテムがすべてアンインストールされます。  
  
 このコマンドでは、[プログラムの追加と削除] に表示されるアプリケーション名と同じアプリケーション名を指定する必要があります。 使用することができます、アプリケーション名のことを確認していない場合は、 **ListPackage** 」の説明に従って、取得するコマンド[ListPackage コマンド](../core/listpackage-command.md)です。  
  
> [!IMPORTANT]
>  .msi ファイルをダブルクリックしてアプリケーションをアンインストールすることもできますが、この方法はサポートの対象外となります。 同じアプリケーションに対して複数の .msi ファイルがインストールされていた場合、この方法では、アプリケーションに関連付けられているアイテムを完全にアンインストールすることはできないためです。  
  
## <a name="usage"></a>使用方法  
 **BTSTask UninstallApp/applicationname は:** *値*  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|Description|  
|---------------|--------------|-----------------|  
|**/ApplicationName** (または**/A**、「解説」を参照してください)|はい|アンインストールする BizTalk アプリケーションの名前。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
  
## <a name="sample"></a>サンプル  
 **Applicationname: myapplication BTSTask UninstallApp**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)