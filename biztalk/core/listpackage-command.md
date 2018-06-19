---
title: ListPackage コマンド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be09b76b-429b-4639-89f0-1eadb0c851ce
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88fca4820dba7c04908e2b756fda0d1d25794a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261962"
---
# <a name="listpackage-command"></a>ListPackage コマンド
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって生成された .msi ファイルに格納されているアイテムを一覧表示します。  
  
## <a name="usage"></a>使用方法  
 **BTSTask ListPackage** [**/パッケージ:***値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|Description|  
|---------------|--------------|-----------------|  
|**/パッケージ**または **/P**|はい|.msi ファイルの名前とパス。 例: C:\MSI\MyApplication.msi。 パスにスペースが含まれる場合は、二重引用符 (") で囲む必要があります。|  
  
## <a name="sample"></a>サンプル  
 **ListPackage/Package:"C:\My MSI files \myapplication.msi"**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)