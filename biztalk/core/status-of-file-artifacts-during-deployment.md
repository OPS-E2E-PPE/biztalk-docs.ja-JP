---
title: デプロイ時にファイルのアイテムの状態 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4f9abe5de90996d883a0c104985e30782a40188
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392927"
---
# <a name="status-of-file-artifacts-during-deployment"></a>デプロイ時にファイルのアイテムの状態
前または処理後のスクリプトを実行するときに、どのようなファイル ベースのアイテムがファイル システムに存在するかを知る必要があります。 たとえば、アンインストール中に実行して、特定のアイテムのファイルをファイル システムから削除する処理後のスクリプトをたい場合があります。 ファイル ベースのアイテムは、BizTalk データベース内の表現に加えて、ローカル ファイル システム上のファイルとして存在できる成果物です。 ファイル ベースのアイテムには、COM コンポーネント、.NET アセンブリ、BizTalk アセンブリ、BAM アイテム、アドホック ファイル、スクリプト、およびバインド ファイルがあります。  
  
 次の表は、展開プロセスの各ポイントで成果物のファイルの状態をまとめたものです。  
  
|展開プロセスをポイントします。|アプリケーション アイテム ファイルの状態|  
|-------------------------------------|------------------------------------------|  
|インストール前|System.BizTalk.File の種類のファイルのみがローカル ファイル システムに存在します。|  
|インストール後|ローカル ファイル システム上のすべてのファイルに存在します。|  
|アンインストール前|ローカル ファイル システム上のすべてのファイルに存在します。|  
|後のアンインストール|すべてのファイルがローカル ファイル システムから削除されています。|  
|前のインポート|ファイルがないローカル ファイル システムで、アプリケーションがローカル コンピューターにインストールされていません。|  
|インポート後|ファイルがないローカル ファイル システムで、アプリケーションがローカル コンピューターにインストールされていません。|  
  
 \* ファイルは、ファイルがアプリケーションに追加されたときに、有効な変換先の場所が指定されている場合にのみ、ローカル ファイル システムに存在します。  
  
## <a name="see-also"></a>参照  
 [処理前および処理後のスクリプトを使用したアプリケーション展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)