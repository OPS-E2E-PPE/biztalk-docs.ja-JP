---
title: UninstallApp コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4fc9da4d645b710490447addc2d4fd8691f199d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292686"
---
# <a name="uninstallapp-command"></a>UninstallApp コマンド
ローカル コンピューターから BizTalk アプリケーションをアンインストールし、アプリケーションを追加でプログラムまたはコントロール パネルの [プログラムの削除] の一覧からも削除されます。 このコマンドでは、追加または削除するプログラムを使用してアプリケーションを削除すると同じ効果があります。 複数の .msi ファイルは、このアプリケーションのインストールされている、すべてのすべての .msi ファイルによってインストールされている項目はアンインストールします。  
  
 追加と削除 に表示される、このコマンドの指定したアプリケーション名は、アプリケーションの名前に一致する必要があります。 アプリケーション名の確信できない場合は使用できます、 **ListPackage** 」の説明に従って、取得するコマンドを[ListPackage コマンド](../core/listpackage-command.md)します。  
  
> [!IMPORTANT]
>  .Msi ファイルをダブルクリックしてアプリケーションをアンインストールすることはできますが、これはサポートされません。 これは、同じアプリケーションの複数の .msi ファイルをインストールすることができます、このメソッドを使用してはアンインストールされませんすべてのアプリケーションに関連付けられている項目のためです。  
  
## <a name="usage"></a>使用方法  
 **BTSTask UninstallApp/applicationname は:** *値*  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|説明|  
|---------------|--------------|-----------------|  
|**/ApplicationName** (または **/A**、「解説」を参照してください)|はい|アンインストールする BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask UninstallApp applicationname:**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)