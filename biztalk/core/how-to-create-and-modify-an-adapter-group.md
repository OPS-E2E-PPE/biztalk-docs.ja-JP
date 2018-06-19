---
title: 作成し、アダプター グループを変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1eef051-2ed7-4e28-8cb9-0145d6c8ed76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6865de8eb67d9fe1a6ca8d93b7d2e6527ae36364
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249226"
---
# <a name="how-to-create-and-modify-an-adapter-group"></a>作成し、アダプター グループを変更する方法
シングル サインオン (SSO) に新たに実装された機能の 1 つに、アダプター グループを作成したり変更したりする機能があります。 アダプター グループとは、その名前からわかるように、複数のアダプターを 1 つにまとめたものです。 アダプター グループを使用することで、一連のアダプターのプロパティ (セキュリティ設定など) を体系的に管理できます。  
  
### <a name="to-create-and-modify-an-adapter-group"></a>アダプター グループを作成および変更するには  
  
1.  ssops ツールの呼び出しを使用して、アダプター グループを作成します。  
  
     関連する XML ファイルで、グループ フラグをアダプター グループとして設定する必要があります。  
  
2.  `ISSOPSAdmin.AddAdapterToAdapterGroup` を使用して、アダプター グループに 1 つまたは複数のアダプターを追加します。  
  
     これでアダプター グループを使用する準備が整います。 必要であれば、`ISSOPSAdmin.GetAdaptersForAdapterGroup` を使用して、関連付けられたアダプターを一覧表示できます。  
  
3.  `ISSOPSAdmin.SetAdapterProperties` を使用して、アダプター グループの設定を変更できます。  
  
4.  以上の作業を終えた後は、`ISSOPSAdmin.RemoveAdapterFromAdapterGroup` を使用して、アダプター グループからアダプターを削除できます。  
  
5.  最後に、`ISSOAdmin.DeleteApplication` を使用して、アダプター グループを削除できます。  
  
     ssops ツールの `-delete` コマンドを使用してアダプター グループを削除することもできます。  
  
## <a name="see-also"></a>参照  
 [パスワードの同期](../core/synchronizing-passwords.md)