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
ms.openlocfilehash: 65e90a4b28d89d4d30b2ca4c6c09977529db653a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328662"
---
# <a name="listpackage-command"></a>ListPackage コマンド
によって生成された .msi ファイルに含まれるアイテムを一覧表示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="usage"></a>使用方法  
 **BTSTask ListPackage** [**/package:**<em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|説明|  
|---------------|--------------|-----------------|  
|**/パッケージ**または **/P**|はい|名前と、.msi ファイルのパス。 例:C:\MSI\MyApplication.msi. パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
  
## <a name="sample"></a>サンプル  
 **ListPackage /Package:"C:\My MSI Files\MyApplication.msi"**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)