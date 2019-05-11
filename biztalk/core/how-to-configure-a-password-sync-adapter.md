---
title: パスワード同期アダプターを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0effdc9b-4aee-4674-90c5-03dfd7cc4cd6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82d86947981455cd3ea0d136726a843d385b210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386984"
---
# <a name="how-to-configure-a-password-sync-adapter"></a>パスワード同期アダプターを構成する方法
パスワード同期アダプターの作成が完了したら、後に、アダプターをシステム上に読み込む必要があります。 さらに、必要がありますに通知するエンタープライズ シングル サインオン (ENTSSO) と、構成ストア アプリケーションのパスワード同期アダプター。 セキュリティのため、構成ストアに登録する必要があります。 アダプターはパスワードとその他の資格情報に更新プログラムを要求します。 そのため、ENTSSO では、このようなアクセス許可を要求する特定のアダプターが許可されているを知る必要があります。  
  
### <a name="to-configure-a-password-sync-adapter"></a>パスワード同期アダプターを構成するには  
  
1.  Ssops ツールを使用して、構成ストアで、アダプターを作成します。  
  
     エンタープライズ シングル サインオンにアプリケーションを説明する構成データベースには、ssops し、XML 構成ファイルを読み込みます。  
  
2.  構成データベースで、アダプターを作成した後でアダプターの情報を変更できます`ISSOPSAdmin.SetAdapterProperties`します。  
  
     2 つの方法は似ていますが、`SetAdapterProperties`構成情報が変更されたときに、アダプターにメッセージを送信します。  
  
3.  アダプターを削除するには、ISSOAdmin.DeleteApplication を使用します。  
  
## <a name="see-also"></a>参照  
 [パスワードの同期](../core/synchronizing-passwords.md)