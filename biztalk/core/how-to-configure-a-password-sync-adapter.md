---
title: パスワード同期アダプターを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 3f0be0146e905ef291942bd30adc111eff89e989
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247354"
---
# <a name="how-to-configure-a-password-sync-adapter"></a>パスワード同期アダプターを構成する方法
パスワード同期アダプターの作成が完了した後で、作成したアダプターをシステム上に読み込む必要があります。 また、エンタープライズ シングル サインオン (ENTSSO) および構成ストアに、アプリケーションがパスワード同期アダプターであることを通知する必要があります。 セキュリティのための構成ストアに登録する必要があります。 アダプターは、パスワードおよびその他の資格情報に更新プログラムが要求されます。 このため、特定のアダプターがこの権限を要求する許可を取得していることを ENTSSO が認識している必要があります。  
  
### <a name="to-configure-a-password-sync-adapter"></a>パスワード同期アダプターを構成するには  
  
1.  ssops ツールを使用して、構成ストアにアダプターを作成します。  
  
     ssops を使用して、構成データベースに XML 構成ファイルを読み込みます。データベースには、エンタープライズ シングル サインオンに対するアプリケーションが記述されます。  
  
2.  アダプターと構成データベースを共に作成すると、`ISSOPSAdmin.SetAdapterProperties` のアダプター情報を変更できます。  
  
     2 つの方法は似ていますが、`SetAdapterProperties` では、構成情報が変更されたときにメッセージがアダプターに送信されます。  
  
3.  アダプターを削除するには、ISSOAdmin.DeleteApplication を使用します。  
  
## <a name="see-also"></a>参照  
 [パスワードの同期](../core/synchronizing-passwords.md)