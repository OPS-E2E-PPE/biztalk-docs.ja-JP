---
title: ListPackage コマンド |Microsoft Docs
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
ms.openlocfilehash: 7c2469a509545dffc80a79a61a5f8f761f5bb724
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970467"
---
# <a name="listpackage-command"></a>ListPackage コマンド
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって生成された .msi ファイルに格納されているアイテムを一覧表示します。  
  
## <a name="usage"></a>使用方法  
 **BTSTask ListPackage** [**/package:**<em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|説明|  
|---------------|--------------|-----------------|  
|**/パッケージ**または **/P**|はい|.msi ファイルの名前とパス。 例: C:\MSI\MyApplication.msi。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
  
## <a name="sample"></a>サンプル  
 **ListPackage/Package:"C:\My MSI \myapplication.msi"**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)