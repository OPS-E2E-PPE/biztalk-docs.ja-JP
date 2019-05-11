---
title: 作成して、アダプター グループを変更する方法 |Microsoft Docs
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
ms.openlocfilehash: ff60beb673515421054863799f7445304a5be200
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339497"
---
# <a name="how-to-create-and-modify-an-adapter-group"></a>作成して、アダプター グループを変更する方法
新しい機能のシングル サインオン (SSO) の 1 つ作成し、アダプター グループを変更する機能があります。 名前が示すように、アダプターのコレクションは、アダプター グループです。 アダプター グループを使用して、アダプターのセキュリティ設定およびその他のプロパティを整理することができます。  
  
### <a name="to-create-and-modify-an-adapter-group"></a>作成し、アダプター グループを変更するには  
  
1.  Ssops ツールへの呼び出しを使用して、アダプター グループを作成します。  
  
     関連付けられている XML ファイルをアダプター グループとしてグループ フラグを設定する必要があります。  
  
2.  使用して 1 つまたは複数のアダプターをアダプター グループに追加`ISSOPSAdmin.AddAdapterToAdapterGroup`します。  
  
     この時点では、アダプター グループが予定どおりに機能する準備ができます。 かどうか、必要に応じて表示する関連付けられているアダプターの完全な一覧を使用して`ISSOPSAdmin.GetAdaptersForAdapterGroup`します。  
  
3.  使用してアダプター グループの設定を変更できます`ISSOPSAdmin.SetAdapterProperties`します。  
  
4.  アダプター グループを使用して、アダプターを削除することができますが完了したら、`ISSOPSAdmin.RemoveAdapterFromAdapterGroup`します。  
  
5.  使用して、アダプター グループを削除する最後に、`ISSOAdmin.DeleteApplication`します。  
  
     使用して、アダプター グループを削除する代わりに選択することがあります、 `-delete` ssops ツールのコマンド。  
  
## <a name="see-also"></a>参照  
 [パスワードの同期](../core/synchronizing-passwords.md)